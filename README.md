# React BEM class-name generator

### Install

```bash
npm i react-bem-classname
```

<br>

### Example
```javascript
import BEMProvider from 'react-bem-classname'

function Human() {
  const style = BEMProvider('human')
  const [isHurt, setHurtState] = useState('false')

  return (
    <section {...style()}>
      <div {...style('::head')} />
      <div {...style('::body')} >
        <div {...style('::arm ::arm:left')} /> 
        <div {...style('::arm ::arm:right', { hurt: isHurt })} /> 
      </div>
      <div {...style('::footer')} >
        <div {...style('::leg ::leg:left')} /> 
        <div {...style('::leg ::leg:right')} /> 
      </div>
    </section>
  )
}
```


### Concept

> TODO
