# Common hooks

Common hooks or hooks not coupled to a specific component.

PS. If the hook is specific to a component, keep it inside of the
component's folder instead.

Example:

```jsx
function usePokemon(id: number) {
  const [data, setData] = React.useState([])
  const [loading, setLoading] = React.useState(false)
  const [error, setError] = React.useState<string>()
  
  React.useEffect(() => {
    (async () => {
      setLoading(true)
      
      const { isOk, data, error } = await getPokemon(id)
      
      if (!isOk) setError(error)
      else setData(data)
      
      setLoading(false)
    })()
  }, [id])
  
  return { pokemon: data, loading, error }
}
```

```jsx
  () => {
    const { pokemon, loading, error } = usePokemon(id)
    ...
  }
```
