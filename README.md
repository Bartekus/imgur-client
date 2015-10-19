imgur-client
======

imgur-client using react react-router reflux and gulp workflow.

#### Screenshot

![Screenshot software](https://raw.githubusercontent.com/Bartekus/imgur-client/master/imgur-client.png "screenshot software")

## Synopsis

Full feature imgur client app

## Code Example

```
module.exports = React.createClass({
  mixins: [
    Reflux.listenTo(ImageStore, 'onChange')
  ],
  getInitialState: function() {
    return {
      image: null
    }
  },
  componentWillMount: function() {
    Actions.getImage(this.props.params.id);
  },
  render: function() {
    return <div className="image-detail">
      {this.state.image ? this.renderContent() : null}
    </div>
  },
  renderContent: function() {
    return <div>
      <div className="panel panel-default">
        <div className="panel-heading">
          <h4>{this.state.image.title}</h4>
        </div>
        <div className="panel-body">
          {this.renderImage()}
        </div>
        <div className="panel-footer">
          <h5>{this.state.image.description}</h5>
        </div>
      </div>
    </div>
  },
  renderImage: function() {
    if(this.state.image.animated) {
      return <video preload="auto" autoPlay="autoplay" loop="loop" webkit-playsinline>
        <source src={this.state.image.mp4} type="video/mp4"></source>
      </video>
    } else {
      return <img src={this.state.image.link} />
    }
  },
  onChange: function() {
    this.setState({
      image: ImageStore.find(this.props.params.id)
    });
  }
});
```

## Motivation

Practical look at React-router combo and reflux patern implementation

### Directory Layout

```
.
├── /.git/                       # Git's hidden repo
├── /node_modules/               # Dependancies source
├── /sass/                       # SASS/SCSS folder
│   ├── /header.scss             # SASS/SCSS header stylesheet
│   ├── /image-detail.scss       # SASS/SCSS single-image stylesheet
│   ├── /image-preview.scss      # SASS/SCSS multiple-image stylesheet
│   ├── /style.scss              # SASS/SCSS main stylesheet
│   └── /topic.scss              # SASS/SCSS topic stylesheet
├── /src/                        # Source folder
│   ├── /components/             # Components source folder
│   │   ├── /header.jsx          # Header component source
│   │   ├── /image-detail.jsx    # Image-single component source
│   │   ├── /image-preview.jsx   # Image-multi component source
│   │   ├── /main.jsx            # App's main loop source
│   │   ├── /topic-list.jsx      # Topic-list component source
│   │   └── /topic.jsx           # Topic component source
│   ├── /stores/                 # Store's source folder
│   │   ├── /comment-store.jsx   # Comment Data Store
│   │   ├── /image-store.jsx     # Image Data Store
│   │   └── /topic-store.jsx     # Topic Data Store
│   ├── /utils/                  # Utilities source folder
│   │   └── /api.jsx             # Api for interaction with imgur
│   ├── /actions.js              # Actions file
│   ├── /app.js                  # App's main loop source
│   └── /routes.jsx              # Router endpoint library
├── .gitignore                   # Version control omission file
├── gulpfile.js                  # Gulp control file
├── index.html                   # Main entry point
├── main.js                      # Main App
├── package.json                 # Dependencies management file
├── README.md                    # This file
├── imgur-client.png             # Picture
└── style.css                    # App's Main stylesheet
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

Basic imgur client that can be use as base for other api projects as well.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

0.3.0 Added comment store along with comment components / Minor adjustments to the CSS / Refactored again
0.2.2 Added view for a single image item / refactored the image store / Adjusted the stylsheets to fix minor glitches
0.2.1 Refactored image-preview / added styles and basic hover functionality (autoplay & stats overlay)
0.2.0 Fixed Rendering & Routing / Added another store for images / topic component adjusted  
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
