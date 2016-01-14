## enzyme-context-bug
This demonstrates the context bug in `enzyme`.

## Behavior
Running `setProps` turns `context` to `undefined`.

## Reproducing
```js
// 1. Use `shallow` as you would (pass `options.context`)
const wrapper = shallow(<MyComponent />, { context: 'yolo' });
// 2. Run an assertion
expect(wrapper.first('div').text()).to.equal('yolo');
// 3. Run `setProps`
wrapper.setProps(5);
// 4. Run the same assertion
expect(wrapper.first('div').text()).to.equal('yolo');
```
