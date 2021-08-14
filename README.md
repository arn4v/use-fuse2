# useFuse2

React hook for fuzzy searching using Fuse.js

## Usage

```tsx
import useFuse from "use-fuse2";
import { useState } from "react";

type BlogPost = {
  title: string;
  content: string;
};

export default function PostList({ data }: { data: BlogPost[] }) {
  const [query, setQuery] = useState("");
  const { result } = useFuse({ data, query });
  return (
    <>
      <input value={query} onChange={(e) => setQuery(e.target.value)} />
      <ul>
        {result.map(({ title }) => (
          <li>{title}</li>
        ))}
      </ul>
    </>
  );
}
```
