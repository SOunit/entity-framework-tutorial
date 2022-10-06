# eager loading

- to avoid multiple query / N + 1 problem
- load data beforehand, not lazy loading

# usage

- string
  - bad practice
  - using magic string
  - `context.Courses.Include("Author")`
- lambda expression
  - `context.Courses.include(c => c.Author)`

# multiple levels

- for single properties

```
context.Courses.Include(c => c.Author.Address)
```

- For collection properties
  - Tags has no Moderator
  - use `Select` to access property in list

```
context.Courses.Include(a => a.Tags.Select(t => t.Moderator))
```
