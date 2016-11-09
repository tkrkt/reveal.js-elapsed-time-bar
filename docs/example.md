# reveal.js Elapsed-Time-Bar Plugin

A [reveal.js](https://github.com/hakimel/reveal.js) plugin adding progress bar of elapsed time,
inspired by [rabbit](https://github.com/rabbit-shocker/rabbit).

Keeping to time in presentations!


## Installation 

Copy the folder ``plugin/elapsed-time-bar`` into plugin folder of your reveal.js project.

Add the plugins to the dependencies and set ``allottedTime`` property, like this:

```js
Reveal.initialize({
  // ...
  
  // your allotted time for presentation
  allottedTime: 3 * 60 * 1000, // 3 minutes
  
  dependencies: [
    // ...

    { src: 'plugin/elapsed-time-bar/elapsed-time-bar.js'}
  ]
});
```


## Configurations

```js
Reveal.initialize({
  // ...

  // - (required) your allotted time for presentation
  allottedTime: 3 * 60 * 1000, // 3 minutes

  // - (optional) height of page/time progress bar
  progressBarHeight: 3,

  // - (optional) bar color
  barColor: 'rgb(200,0,0)',

  // - (optional) bar color when timer is paused
  pausedBarColor: 'rgba(200,0,0,.6)',
});
```


## API

You can use APIs from global ``ElapsedTimeBar`` object.

|property name|description|
|---|---|
|<a href="javascript:alert(ElapsedTimeBar.isPaused)">isPaused</a>|true if timer is paused|
|<a href="javascript:alert(ElapsedTimeBar.isFinished)">isFinished</a>|true when you run out of your allotted time|
|<a href="javascript:ElapsedTimeBar.start(30000, 10000)">start(allottedTime [,elapsedTime=0])</a>|start timer with new allotted time|
|<a href="javascript:ElapsedTimeBar.reset()">reset()</a>|reset timer|
|<a href="javascript:ElapsedTimeBar.pause()">pause()</a>|pause timer|
|<a href="javascript:ElapsedTimeBar.resume()">resume()</a>|resume timer|


## Keyboard binding example

Press Enter or 'r' key!

```js
Reveal.initialize({
  // ...

  keyboard: {
    // pause/resume time when Enter is pressed
    13: () => {
      ElapsedTimeBar.isPaused ? ElapsedTimeBar.resume() : ElapsedTimeBar.pause();
    },
    // reset timer when 'r' is pressed
    82: () => {
      ElapsedTimeBar.reset();
    }
  }
});
```


# Licence

MIT