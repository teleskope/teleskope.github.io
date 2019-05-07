# Schema definitions

# Profile
```
{
  owner: { type: String, required: true },
  role: { type: String, required: true },
  firstName: { type: String, required: true },
  lastName: { type: String, required: true },
  website: String,
  socials: { type: Array },
    'socials.$': Object,
    'socials.$.provider': String,
    'socials.$.link': String,
  zipCode: String,
  following: Array,
  'following.$': String,
  skills: Array,
  'skills.$': String,
  summary: String,
  /* Find a way to have user input experiences individually, such as separate fields etc */
  experience: String,
  image: String,
}
```

# Company
```
{
  name: { type: String, required: true },
  address: { type: String, required: true },
  zipCode: { type: String, required: true },
  website: String,
  summary: String,
  owners: { type: Array, required: true },
  image: String,
  'owners.$': String,
  socials: { type: Array },
  'socials.$': Object,
  'socials.$.provider': String,
  'socials.$.link': String,
  jobs: { type: Array },
    'jobs.$': Object,
    'jobs.$.title': String,
    'jobs.$.employmentType': {
      type: String,
      allowedValues: ['Full Time', 'Part Time'],
      defaultValue: 'Full Time',
    },
    'jobs.$.date': String,
    'jobs.$.description': String,
    'jobs.$.zipCode': String,
    'jobs.$.requirements': String,
    'jobs.$.skills': Array,
    'jobs.$.skills.$': String,
  notifications: { type: Array },
    'notifications.$': Object,
    'notifications.$.datetime': Date,
    'notifications.$.content': String,
}
```

# Skills
```
{
  name: String,
  description: String,
}
```


# Model Mongo Actions Example (Stuff)
```
// app/imports/startup/server/stuff.js
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
