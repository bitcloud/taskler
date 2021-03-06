# Taskler
> Listr inspired Terminal task list but with callbacks instead of promises & observables

## Install
```cl
yarn add taskler
```

## Usage
```js
const taskler = require('taskler')

const tasks = [{
  title: 'Do something',
  task: ({emit, succeed}) => {
    emit('start')

    setTimeout(() => {
      emit('still working...')
    }, 1000)

    setTimeout(() => {
      succeed()
    }, 2000)
  }
}, {
  title: 'Another task',
  task: ({emit, succeed}) => {
    emit('also starting..')

    setTimeout(() => {
      succeed()
    }, 1500)
  }
}]

taskler(tasks, () => {
  console.log('🎉  All tasks are done')
})
```
## Preview
![Preview](https://mjz.io/D1Ohh.gif)
