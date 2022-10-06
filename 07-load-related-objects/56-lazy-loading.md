# immediate execution

- `single`
- `first`
- `count`
- `max`
- `average`

- related objects are not loaded immediately

```
// immediate execution
var course = context.Courses.Single(c => c.ID == 2);

// lazy loading
foreach(var tag in course.Tags){
  console.log(tag.Name);
}
```
