# jest

## The Problem it Solve
test platform and give a lot of test methods

## Matchers
- `toBe`
- `toEqual`
- `toMatch`
- `toContain`
- `toBeFalsy`, `toTruthy`
- `toBeGreaterThan`, `toBeLessThan`
- `toThrow`

## Test Asynchronous Code
```javascript
test('the data is peanut butter', () => {
  return fetchData().then(data => {
    expect(data).toBe('peanut butter');
  });
});

test('the data is peanut butter', () => {
  return expect(fetchData()).resolves.toBe('peanut butter');
});

test('the data is peanut butter', async () => {
  const data = await fetchData();
  expect(data).toBe('peanut butter');
});
```

## Handle setup work
setup work like init database, init collection
- `beforeEach`, `afterEach` => every test will call
- `beforeAll`, `afterAll` => call once, every test will have its context
- `scoping` => `describe`, `only`

## Mock Function <Best Feature `jest` Provide>
There are two ways to mock functions: 
- `jest.fn()`: return an mock function with some useful properties:
  + `mock`: `mock.calls`, `mock.results`, `mock.instances`;
  + `bind`: like javascript `Function.bind()`;
  + `mockReturnValueOnce`
- `jest.mock()`: mock modules, when mock successfully, all funcion that exposed within an moudle can be mocked;
  + module.somefunction.`mockResolvedValue`
  + partial mock, like:
    ```javascript
    //test.js
    import defaultExport, {bar, foo} from '../foo-bar-baz';

    jest.mock('../foo-bar-baz', () => {
    const originalModule = jest.requireActual('../foo-bar-baz');

    //Mock the default export and named export 'foo'
    return {
        __esModule: true,
        ...originalModule,
        default: jest.fn(() => 'mocked baz'),
        foo: 'mocked foo',
    };
    });
    ```
  + somefunction.`mockImplementation()`

## Snapshot Testing