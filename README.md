# ts-proto incompatibility with TypeScript >=5.6

This repo shows the incompatibilities of ts-proto 2.4.2 with TypeScript >= 5.6, where the generated code cannot compile with error 

```
generated/test.ts:125:65 - error TS2345: Argument of type 'Buffer' is not assignable to parameter of type 'BinaryReader | Uint8Array'.
  Type 'Buffer' is not assignable to type 'Uint8Array'.
    The types returned by 'entries()' are incompatible between these types.
      Type 'IterableIterator<[number, number]>' is missing the following properties from type 'ArrayIterator<[number, number]>': map, filter, take, drop, and 9 more.

125     responseDeserialize: (value: Buffer) => TestResponse.decode(value),
```

```bash
# Generate code
pnpm generate

# Compile code
pnpm build
```