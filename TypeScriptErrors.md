## How do I fix the following error
## Table of Content

### ERROR: Type '{ props: Props | undefined; }' is not assignable to type 'IntrinsicAttributes & Props'. Property 'props' does not exist on type 'IntrinsicAttributes & Props'.ts(2322)

- Problem
```
type Props = {
  ...
}

const Parent = ():JSX.Element => {
  return {
    // =================================================================================================== //
    // ERROR: Type '{ props: Props | undefined; }' is not assignable to type 'IntrinsicAttributes & Props'.
    // ERROR: Property 'props' does not exist on type 'IntrinsicAttributes & Props'.ts(2322)
    // =================================================================================================== //
    < Child props={props} />
  }
}

const Child = (props: Props): JSX.Element => {
  ...
```

- Solution
```
type Props = {
  ...
}

const Parent = ():JSX.Element => {
  return {
    < Child props={props} />  // Fixed
  }
}

type ChildProps = {
    props: Props
}
const Child = ({ props } : ChildProps): JSX.Element => {
  ...
```
