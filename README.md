# react-native-floating-action-bar

A React Native floating action bar.

|                   Horizontal action bar                    |                  Vertical action bar                   |
| :--------------------------------------------------------: | :----------------------------------------------------: |
| ![Horizontal action bar](assets/horizontal-action-bar.png) | ![Vertical action bar](assets/vertical-action-bar.png) |

## The Fork

This project has been modified to supply the external navigation control facilities.

## Installation

_npm_

```shell
$ npm i react-native-floating-action-bar --save
```

_yarn_

```shell
$ yarn add react-native-floating-action-bar
```

_Additional package install_

This project depends (for now) on [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons). If you dont have this package already in your project, please add this by following [react-native-vector-icons installation instructions](https://github.com/oblador/react-native-vector-icons#installation).

## Usage

_import_

```javascript
import FloatingActionBar from 'react-native-floating-action-bar';
```

_basic_

```javascript
<FloatingActionBar
  items={[{icon: 'taxi'}, {icon: 'subway'}, {icon: 'train'}, {icon: 'bus'}]}
  onPress={handlePress}
/>
```

_maxed out_

```javascript
<FloatingActionBar
  items={[
    {
      icon: 'taxi',
      color: 'rgb(130, 130, 130)',
      activeColor: 'rgb(3, 137, 253)',
      activeBackgroundColor: 'rgb(224, 243, 255)',
    },
    {
      icon: () => <Icon name="subway" />,
      color: 'rgb(130, 130, 130)',
      activeColor: 'rgb(3, 137, 253)',
      activeBackgroundColor: 'rgb(224, 243, 255)',
    },
    {
      icon: ({active}) => (
        <Icon
          name="train"
          color={active ? 'rgb(3, 137, 253)' : 'rgb(130, 130, 130)'}
        />
      ),
      color: 'rgb(130, 130, 130)',
      activeColor: 'rgb(3, 137, 253)',
      activeBackgroundColor: 'rgb(224, 243, 255)',
    },
    {
      icon: ({active, activeColor, color, icon, size}) => (
        <Icon name={icon} size={size} color={active ? activeColor : color} />
      ),
      color: 'rgb(130, 130, 130)',
      activeColor: 'rgb(3, 137, 253)',
      activeBackgroundColor: 'rgb(224, 243, 255)',
    },
  ]}
  offset={50}
  onPress={handlePress}
  position="bottom"
  selectedIndex={0}
  style={styles.floatingActionBar}
/>
```

## Interface

### items

Accepts an array with objects. The object is used to generate and style the action bar items.

_item interface_

```
{
  icon: 'taxi' || Your own icon render function,
  color: 'rgb(130, 130, 130)', // optional
  activeColor: 'rgb(3, 137, 253)', // optional
  activeBackgroundColor: 'rgb(224, 243, 255)', // optional
}
```

### offset (optional)

Accepts a number. Offsets the action bar by given number.

### position (optional)

Accepts a string containing one of these types: `top`, `bottom`, `left`, `right`.
This property positions the action bar to the given position. With `top` or `bottom` the action bar renders as a row, with `left` or `right` the action bar renders as a column.

### onPress (optional)

Accepts a function. returns the selected index.

### selectedIndex (optional)

Accepts an int. Can be used to set initial index.

### style (optional)

Accepts a StyleSheet style or an object. This allows you to style the container.

## Contributing

Issues are welcome. The best way to report a problem is to reproduce it with a code example.

Pull requests are welcome. If you want to change the API, it's better to discuss it using an issue ticket.

## License

react-native-floating-action-bar is [MIT licensed](./LICENSE).
