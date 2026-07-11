# espeditor
ESP light weight web based code editor

## 1. Install
```javascript
npm install microlight
```
## 2. Create a component
```javascript
import { useEffect } from "react";
import microlight from "microlight";

export default function CodeBlock() {
  useEffect(() => {
    microlight.reset();
  }, []);

  const code = `
function hello(name) {
  console.log("Hello " + name);
}
`;

  return (
    <pre className="microlight">
      {code}
    </pre>
  );
}
```
## 3. Re-highlight when the code changes
```javascript
import { useEffect } from "react";
import microlight from "microlight";

function CodeBlock({ code }) {
  useEffect(() => {
    microlight.reset();
  }, [code]);

  return (
    <pre className="microlight">
      {code}
    </pre>
  );
}
```
## 4. With <code> inside <pre>
```html
<pre className="microlight">
  <code>{code}</code>
</pre>
```
## 5. Example with state
```javascript
import { useState, useEffect } from "react";
import microlight from "microlight";

export default function App() {
  const [code, setCode] = useState(
`const x = 10;

console.log(x);`
  );

  useEffect(() => {
    microlight.reset();
  }, [code]);

  return (
    <>
      <textarea
        value={code}
        onChange={(e) => setCode(e.target.value)}
        rows={8}
        cols={60}
      />

      <pre className="microlight">
        {code}
      </pre>
    </>
  );
}
```

## Sources
```
https://asvd.github.io/microlight/
https://github.com/rcarubbi/ReactBlocklyEditor
```

