# ReactJS Style Guide

This styleguide is based on [Khan Academy's ReactJS Styleguide](https://github.com/Khan/style-guides/blob/master/style/react.md).

Follow the normal [JavaScript style guide](javascript.md) - including the 80
character line limit and the [HTML Style Guide](html.md). In addition, there are
several React-specific rules.

## Formatting

* Order your methods with lifecycle first and render last. Like so:
  1. lifecycle methods (in chronological order:
        `getDefaultProps`,
        `getInitialState`,
        `componentWillMount`,
        `componentDidMount`,
        `componentWillReceiveProps`,
        `shouldComponentUpdate`,
        `componentWillUpdate`,
        `componentDidUpdate`,
        `componentWillUnmount`)
  2. everything else
  3. `render`
* Start private componentn method names with an `_`.
* Name handlers with the `handle` prefix: `handleEventName`. Example:
  ```jsx
  <Component onClick={this._handleClick} onLaunchMissiles={this._handleLaunchMissiles} />
  ```
* Name handlers in props `onEventName`. This is consistent with React's event
  naming: `onClick`, `onDrag`,`onChange`, etc. Example:
  ```jsx
<Component onLaunchMissiles={this.handleLaunchMissiles} />
  ```

* Use parentheses to wrap the component expressions. Example:
  ```jsx
  return (
    <div>
      ...
    </div>
  );
  return (<span>Onliner</span>);
  ```

* Align and sort HTML properties to one indentation level, when all the
properties don't fit in one line. Example:
  ```jsx
<li
  className="card card--secondary"
  onClick={this._handleClick}
  onClick={this._handleClick}
  ```

* Write the HTML attributes in this particular order:
  1. `class`
  2. `id`, `name`
  3. Event handlers
  4. `src`, `for`, `type`, `href`, `value`
  5. `title`, `alt`
  6. `aria-*`, `role`

## General

* Make "presentation" (dumb) components pure, and name them according to their
  presentational semantics, not according to the use that they will have (e.g.
  `SliderItem` not `SliderUser`). See more about it [here](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0).
  * Prefer [props to state](http://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html#what-components-should-have-state).
  You almost always want to use props. By avoiding state when possible, you
  minimize redundancy, making it easier to reason about your application.

* Use [propTypes](http://facebook.github.io/react/docs/reusable-components.html).
  React Components should always have complete `propTypes`. Every attribute of
  `this.props` should have a corresponding entry in `propTypes`. This documents
  that props need to be passed to a model.

* Never store state in the DOM. Do not use `data-` attributes or classes. All
  information should be stored in JavaScript, either in the React component
  itself, or in a React store if using a framework such as Redux.

## References

* [Khan Academy's ReactJS Styleguide](https://github.com/Khan/style-guides/blob/master/style/react.md)
