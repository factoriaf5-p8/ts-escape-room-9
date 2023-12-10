# Typescript Labs

## Lab 9: Typing Promises and Async Requests

file: `/src/09-promises.problem.ts`

Here we have a function called `fetchLukeSkywalker`:

```ts
export const fetchLukeSkywalker = async (): LukeSkywalker => {
  const data = await fetch("<https://swapi.dev/api/people/1>").then((res) => {
    return res.json();
  });

  return data;
};
```

It goes to the Star Wars API at swapi.dev and fetches people/1, which happens to correspond to Luke Skywalker.

There's a LukeSkywalker type that includes properties based on what the API includes in the response:

```ts
interface LukeSkywalker {
  name: string;
  height: string;
  mass: string;
  hair_color: string;
  skin_color: string;
  eye_color: string;
  birth_year: string;
  gender: string;
}
```

However, TypeScript is showing us an error on the return type:

`Type 'LukeSkywalker' is not a valid async function return type in ES5/ES3 because it does not refer to a Promise-compatible constructor value.`

Challenge
Your challenge is to figure out how to update the return type annotations to make TypeScript happy.