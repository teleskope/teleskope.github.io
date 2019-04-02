# Schema definitions

# User
```
{
  firstName: String, 
  lastName: String,
  email: String,
  password: String,
  linkedin: String,
  twitter: String,
  github: String,
  image: String,
}
```

# Student extends User
```
{
  super
  name: String,
  website: String,
  skills: Array[skill_ids],
  summary: Text,
  experience: Array,
}
```

# Admin extends User
```
{
  super
  name: String,
}
```

# Company
```
{
  name: String,
  website: String,
  address: String,
  zipcode: String,
  skills: Array[skill_ids],
  size: Integer, 
  contact: String,
  summary: Text,
}
```


# Skills
```
{
  name: String,
  description: Text,
}
```