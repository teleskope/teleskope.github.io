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

# Company extends User
```
{
  super
  companyName: String,
  website: String,
  address: String,
  zipCode: String,
  skills: Array[skill_ids],
  size: Integer, 
  contact: String,
  summary: String,
}
```


# Skills
```
{
  name: String,
  description: Text,
}
```


# Schema Example (Stuff)
```
import { Meteor } from 'meteor/meteor';
import { Roles } from 'meteor/alanning:roles';
import { Stuffs } from '../../api/stuff/stuff.js';

/** Initialize the database with a default data document. */
function addData(data) {
  console.log(`  Adding: ${data.name} (${data.owner})`);
  Stuffs.insert(data);
}

/** Initialize the collection if empty. */
if (Stuffs.find().count() === 0) {
  if (Meteor.settings.defaultData) {
    console.log('Creating default data.');
    Meteor.settings.defaultData.map(data => addData(data));
  }
}

/** This subscription publishes only the documents associated with the logged in user */
Meteor.publish('Stuff', function publish() {
  if (this.userId) {
    const username = Meteor.users.findOne(this.userId).username;
    return Stuffs.find({ owner: username });
  }
  return this.ready();
});

/** This subscription publishes all documents regardless of user, but only if the logged in user is the Admin. */
Meteor.publish('StuffAdmin', function publish() {
  if (this.userId && Roles.userIsInRole(this.userId, 'admin')) {
    return Stuffs.find();
  }
  return this.ready();
});

```
