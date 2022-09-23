# Data layer
Write all your data fetching logic here instead of inside of the component. You may also want to create a custom hook for consuming this data.

Example:
```
|
|-services
|--api.ts
|--pokemon
|---index.ts
|---types.ts
|
```

```
/* /services/pokemon/index.ts */

type Pokemon = {
  id: number;
  name: string;
  types: {
    id: number;
    name: string
  }[]  
}

async function getPokemon(id: number) {
  try {
    const raw = await api.get(`/pokemon/${id}`)
    
    const data: Pokemon[] = raw.data.results.map(result => ({
      id: getIdFromUrl(result.url),
      name: result.name,
      types: result.types(type => ({
        id: getIdFromUrl(type.type.url),
        name: type.type.name
      }))
    }))

    return {
      isOk: true,
      pokemon: data,
      error: null
    }
  } catch(e) {    
    return {
      isOk: false,
      pokemon: [],
      error: (e as Error).message
    }  
  }
}
```
