### input
To mark the start of jsxtmpl, open tag `<<type>>` and closing tag `<</>>` or
`<</type>>`

```
* Input A
  ```
  foo bar <baz />
  ```

* Input B
  ```
  </ assume users is array looking like [{ name:"John Doe", age: 52 }, ...] />
  <users>
    {users.map(usr => {
      const [ firstname, lastname ] = usr.name.split();
      return (
        <{firstname, lastname} age={user.age}>
      );
    })}
  </>
  ```

### output
#### raw
A:
```
foo bar baz
```

B:
```
users
  firstnameJohn lastnameDoe age52
```

#### as JSON
A:
```
{
  "users": 
```

B:
```
["foo bar ", "baz"]
```

#### as YAML
A:
```
- foo bar 
- baz
```
