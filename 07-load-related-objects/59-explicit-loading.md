# explicit loading

- separate queries
- multiple round-trips

# eager loading

- uses joins
- one round-trip

# MDN approach

- only for single entry - for 1 author only

```
context.Entry(author).Collection(a => a.Courses).Query().Where(c => c.FullPrice == 0).Load();
```

# Mosh recommended approach

```
context.Courses.Where(c => c.AuthorId == author.Id && c.FullPrice == 0).Load();
```

# In operator

```
select *
from courses
where AuthorID in (1,2,3)
```

```
var author = context.Authors.toList();
var authorIds = authors.Select(a => a.Id);
context.Courses.Where(c => authorIds.Contains(c.AuthorId) && c.FullPrice == 0).Load();
```
