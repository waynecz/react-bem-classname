# React BEM className generator

#### Supporting facilities
1. [watson-scss](https://github.com/waynecz/Watson) for writing nested BEM  fastly and furiously.
2. [watson-snippet](https://github.com/waynecz/watson-snippet) vscode extension for coding faster.

<br>

### Install

```bash
npm i react-bem-classname -S
```

<br>

### Example
```javascript
import BEMProvider from 'react-bem-classname'

function Human() {
  // recommend use bem as variable name cuz 
  const bem = BEMProvider('human')
  const [isHurt, setHurtState] = useState('false')

  return (
    <section {...bem()}>
      <div {...bem('::head')} />
      <div {...bem('::body')} >
        <div {...bem('::arm :left')} /> 
        <div {...bem('::arm :right', { hurt: isHurt })} /> 
      </div>
      <div {...bem('::footer')} >
        <div {...bem('::leg :left')} /> 
        <div {...bem('::leg :right')} /> 
      </div>
    </section>
  )
}
```

code above is exactly equal to this:

```jsx
function Human() {
  const [isHurt, setHurtState] = useState('false')

  return (
    <section className="human">
      <div className="human_head" />
      <div className="human_body" >
        <div className="human_arm human_arm--left" /> 
        <div className={`human_arm human_arm--right ${isHurt ? 'is-hurt' : ''}`} /> 
      </div>
      <div className="human_footer" >
        <div className="human_leg human_leg--left" /> 
        <div className="human_leg human_leg--left" /> 
      </div>
    </section>
  )
}
```


### Basic concept

+ Use `::pseudo element` as Block's Element
+ Use `:pseudo class` as Modifier
