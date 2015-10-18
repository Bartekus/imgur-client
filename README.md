imgur-client
======

imgur-client using react react-router reflux and gulp workflow.

#### Screenshot

![Screenshot software](https://raw.githubusercontent.com/Bartekus/imgur-client/master/imgur-client.png "screenshot software")

## Synopsis

Full feature imgur client app

## Code Example

```
getInitialState: function() {
  return {
    topics: []
  }
},
```

## Motivation

Practical look at React-router combo and reflux patern implementation

### Directory Layout

```
.
├── /.git/                       # Git's hidden repo
├── /node_modules/               # Dependancies source
├── /sass/                       # SASS/SCSS folder
│   └── /style.scss              # SASS/SCSS stylesheet
├── /src/                        # Source folder
│   ├── /components/             # Components source folder
│   │   ├── /header.jsx          # Header component source
│   │   ├── /main.jsx            # App's main loop source
│   │   └── /topic-list.jsx      # Topic-list component source
│   ├── /utils/                  # Utilities source folder
│   │   └── /api.jsx             # Api for interaction with imgur
│   ├── /app.js                  # App's main loop source
│   └── /routes.jsx              # Router endpoint library
├── .gitignore                   # Version control omission file
├── gulpfile.js                  # Gulp control file
├── index.html                   # Main entry point
├── main.js                      # Main App
├── package.json                 # Dependencies management file
├── README.md                    # This file
└── imgur-client.png             # Picture
```

## Installation

Checkout this repo, install dependencies, then open index file with the following:

```
  > git clone git@github.com:Bartekus/imgur-client.git
  > cd imgur-client
  > npm install
  > gulp (might have to execute: npm install -g gulp)
```

## Usage

Basic imgur client...

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

0.1.1 Refactored header, Added matching parameters to routing / adjusted look of the content
0.1.0 Refactoring to reflux flow patter completed / Actions along with reflex listenables have been added as well
0.0.4 Added store and mixins/ Ongoing refactoring
0.0.3 Refactored to keep code DRY
0.0.2 Basic Functionality Completed
0.0.1 First Commit - Basic Structure

## Tests

Basic non-automated manual browser test aka no test :P

## Contributors

Standing on the shoulders of all the giants before me.

## Contact
#### Bartek Kus
* Homepage: http://bartekus.com
* E-mail: bartekus@gmail.com
* Twitter: [@Bartekus](https://twitter.com/Bartekus "Bartekus on twitter")

## License

Copyright (c) 2015 Bartek Kus

Licensed under the MIT license
