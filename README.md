# CodeSwarm

## Install

Checkout plugin `codeswarm-node`:

```
$ cd projects
$ git clone git@github.com:CodeSwarm/codeswarm-node.git
$ cd codeswarm-node
$ npm link
```

Checkout plugin `codeswarm-sauce`:

```
$ cd projects
$ git clone git@github.com:CodeSwarm/codeswarm-sauce.git
$ cd codeswarm-sauce
$ npm link
```

Checkout plugin `codeswarm-plato`:

```
$ cd projects
$ git clone git@github.com:CodeSwarm/codeswarm-plato.git
$ cd codeswarm-plato
$ npm link
```

Checkout plugin `codeswarm-custom`:

```
$ cd projects
$ git clone git@github.com:CodeSwarm/codeswarm-custom.git
$ cd codeswarm-custom
$ npm link
```

Checkout plugin `codeswarm-gateway`:

```
$ cd projects
$ git clone git@github.com:CodeSwarm/codeswarm-gateway.git
$ cd codeswarm-gateway
$ npm link
```

Link them:

```
$ cd  projects/codeswarm
$ npm link codeswarm-node
$ npm link codeswarm-sauce
$ npm link codeswarm-plato
$ npm link codeswarm-custom
```

## Run

Start CodeSwarm in dev mode (uses nodemon to restart when JS changes are made):

```bash
$ npm run mon
```


## CouchDB Setup

You have to create the admin user with the `admin` password. You can override this with the COUCHDB_USERNAME and COUCHDB_PASSWORD env vars though.

To add the couchdb admin user go to futon (the couchdb admin interface), and click on the `Setup more admins` on the bottom right side.
On the couchdb configuration, set couchdb_httpd_auth=> allow_pesistent_cookies to true
Make sure the admin user is listed on the config `admins` section

Using a different user on the fronted than the admin user and also the persistent cookie session should prevent you from being logged out.

### Session timeout

To define / redefine the session timeout you need to specify the `timeout` parameter of the `couch_httpd_auth` section of the configuration, in seconds:

![session timeout](docs/images/session_timeout.png)


## Admin rights

In order to add foreign projects (projects you are not a github admin of), you need to bead admin rights.

To give a user admin rights go to the `_users` database in CouchDB and edit the relevant user.
Edit the `roles` attribute and add an `admin` value to it. Save the user document.

The user must logout and login in order to get the privileges.

## Sponsors

We'd like to thank the sponsors of this project for the generous support.

* [Microsoft Internet Explorer](http://modern.ie)
* [appendTo](http://appendTo.com)
* [Code Summit](http://codesummit.com)

## License Information

This project has been released under the [Apache License, version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html), the text of which is included below. This license applies ONLY to the source of this repository and does not extend to any other CodeSwarm distribution or variant, or any other 3rd party libraries used in a repository. 

> Copyright © 2014 CodeSwarm, Inc.

> Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

> [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

>  Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
