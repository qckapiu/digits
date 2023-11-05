# Digits

![](<img src="doc/landing.png">)

digits is an application that: 

  * allows users to add/edit contacts
  * save and store information such as names, addresses, and phone numbers
  * add timestamped notes for each contact

## Installation

First, [install Meteor](https://www.meteor.com/install).

Second, download [digits](https://github.com/qckapiu/digits). Digits is a private repo so you will need to request permission to gain access.

Third, cd into the app/ directory of your local copy of the repo, and install third party libraries with:

```
$ meteor npm install
```

Once it has been installed, you can run the application with:

```
$ meteor npm run start
```

The first time you run the app, default users and contacts will be generated.

```
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ ~/Documents/GitHub/digits/app ]]]]]     

=> Started proxy.                             
=> Started HMR server.                        
=> Started MongoDB.                           
I20231104-19:24:37.026(-10)? Creating the default user(s)
I20231104-19:24:37.036(-10)?   Creating user admin@foo.com.
I20231104-19:24:40.066(-10)?   Creating user john@foo.com.
I20231104-19:24:40.657(-10)? Creating default contacts.
I20231104-19:24:40.657(-10)?   Adding: Johnson (john@foo.com)
I20231104-19:24:40.910(-10)?   Adding: Casanova (john@foo.com)
I20231104-19:24:40.913(-10)?   Adding: Binsted (admin@foo.com)
=> Started your app.

=> App running at: http://localhost:3000/
```

## Viewing the running app

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000).  You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config/settings.development.json), or else register a new account.

## ESLint

You can verify that the code obeys our coding standards by running ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```

## User Interface Walkthrough

### Landing Page
When the application is first viewed on [http://localhost:3000](http://localhost:3000), you will reach the landing page that includes the a brief description of Digits.

![](<img src="doc/landing.png">)

### Login page

Clicking on the Login link, then on the Sign In menu item displays this page:

![](<img src="doc/signin.png">)

### Register page

Alternatively, clicking on the Login link, then on the Sign Up menu item displays this page:

![](<img src="doc/signup.png">)


### User home page

Once you log in (either to an existing account or by creating a new one), the navbar changes as follows:

![](<img src="doc/userhome.png">)

You can now add new contacts, and list the contacts you have created. Note you cannot see any contacts created by other users.

### Add Contact page

After logging in, here is the page that allows you to add new Stuff:

![](<img src="doc/addcontact.png">)

### List Contact page

After logging in, here is the page that allows you to list all the contacts you have created:

![](<img src="doc/listcontacts.png">)

You click the "Edit" link to go to the Edit Contact page, shown next.

### Edit Contact page

After clicking on the "Edit" link associated with an item, this page displays that allows you to change and save it:

![](<img src="doc/editcontact.png">)

### Admin home page

You can define an "admin" user in the settings.development.json file. This user, after logging in, gets a special "admin" entry in the navbar.

The Admin page lists all of the contacts by all of the users:

![](<img src="doc/admin.png">)

Note that non-admin users cannot get to this page, even if they type in the URL by hand.

## Collections

The application implements the Collections called "Contacts" and "Notes". Each Contact document has the following fields: firstName, lastName, address, image, description, owner, and _id. Each Note document has the following fields: note, contactId, owner, createdAt, and _id.

The Contacts collection is defined in [imports/api/contact/contacts.js](https://github.com/qckapiu/digits/blob/main/app/imports/api/contact/Contacts.js).

The Notes collection is defined in [imports/api/note/notes.js](https://github.com/qckapiu/digits/blob/main/app/imports/api/note/Notes.js).

The Contacts and Notes collection are initialized in [imports/startup/server/Mongo.js](https://github.com/qckapiu/digits/blob/main/app/imports/startup/server/Mongo.js).

## Routing

For display and navigation among its four pages, the application uses [React Router](https://reacttraining.com/react-router/).

Routing is defined in [imports/ui/layouts/App.jsx](https://github.com/qckapiu/digits/blob/main/app/imports/ui/layouts/App.jsx).
