# vue-mapbox
> MapboxGL component for Vue.js

This module is based on source code of [vue-mapbox-gl](https://github.com/phegman/vue-mapbox-gl).

## Getting started

Here's how to install and use this module.

### Installation

You can install this module via `npm` and `yarn`.
#### NPM
``` bash
$ npm install --save vue2-mapbox
```
#### Yarn
``` bash
$ yarn add vue2-mapbox
```

### Setup

To use this module just import it into component you want to use it in.
Also to use it it's needed to manualy import css file.
``` javascript
import Mapbox from 'vue2-mapbox'
import 'mapbox-gl/dist/mapbox-gl.css'

export default {
	components: {
		Mapbox
	}
}
```

Now you can use `Mapbox` tag in your HTML.
``` html
<div>
	<Mapbox></Mapbox>
</div>
```

## Usage

### Props

`access-token`	
Type: `String`	
Required: `true`

Your public access token is required for use of Mapbox API. It can be obtained in the Mapbox Studio dashboard.

---
`map-options`	
Type: `Object`	
Required: `true`

Overview of available Mapbox options can be found [here](https://www.mapbox.com/mapbox-gl-js/api/#map).

---
`nav-control`	
Type: `Object`	
Required: `false`	
Default:
``` javascript
{
	show: false,
	position: 'top-left',
	options: {}
}
```

More information about navigation control [here](https://www.mapbox.com/mapbox-gl-js/api/#navigationcontrol).

---
`geolocate-control`	
Type: `Object`	
Required: `false`	
Default:
``` javascript
{
	show: false,
	position: 'top-left',
	options: {}
}
```

More information about geolocate control [here](https://www.mapbox.com/mapbox-gl-js/api/#geolocatecontrol).

---
`scale-control`	
Type: `Object`	
Required: `false`	
Default:
``` javascript
{
	show: false,
	position: 'top-left',
	options: {}
}
```

More information about scale control [here](https://www.mapbox.com/mapbox-gl-js/api/#scalecontrol).

---
`fullscreen-control`
Type: `Object`
Required: `false`
Default:
``` javascript
{
	show: false,
	position: 'top-right'
}
```

More information about full screen control [here](https://www.mapbox.com/mapbox-gl-js/api/#fullscreencontrol).

---
`markers`	
Type: `Array`	
Required: `false`
Default: `[]`

Here you can pass locations for markers and the description of a popup that will show up when marker is clicked.

Example:
``` javascript
[
	{
		location: [-96, 37.8],
		title: 'some location',
		body: 'some location description and popup body (it can also be html)'
	}
]
```

### Example
``` html
<Mapbox
	access-token="your public access token"
	:map-options="{
		style: 'mapbox://styles/mapbox/light-v9',
		center: [-96, 37.8],
		zoom: 3
	}"
	:geolocate-control="{
		show: true,
		position: 'top-left'
	}"
	:scale-control="{
		show: true,
		position: 'top-left'
	}"
	:fullscreen-control="{
		show: true,
		position: 'top-left'
	}"
></Mapbox>
```

### Events

All Mapbox GL JS events are available for use. You can find the list of events [here](https://www.mapbox.com/mapbox-gl-js/api/#map.event:resize).

Map and control events can be used by adding a prefix introduced in the following table to the beginning of Mapbox event name.

| Object           | Prefix       |
| ------           | ------       |
| Map              | `map-`       |
| GeolocateControl | `geolocate-` |

For example for the Mapbox map `click` event `@map-click` will be used and for the GeolocateControl geolocate event `@geolocate-geolocate` will be used.

All events are passed the `map` or `control` object and the event or position object if it has one.

## Maintainers
 - [Dušan Simić](http://dusansimic.me)
