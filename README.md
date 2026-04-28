# jammin + as-lan Template

This project was created with [jammin](https://github.com/FluffyLabs/jammin), FluffyLabs' toolbox for JAM service builders. It uses the [as-lan](https://github.com/tomusdrw/as-lan) AssemblyScript SDK for building JAM services.

## Getting Started

Install the jammin CLI by following the [installation guide](https://fluffylabs.dev/jammin/getting-started.html).

This project includes:

- Pre-configured as-lan service in `services/example`
- Build configuration in `jammin.build.yml`
- Fibonacci example as the starter service logic — edit `services/example/assembly/service.ts` to replace it with your own

## Available Commands

### Build

```bash
jammin build
```

Runs the build inside the as-lan Docker image. Produces `services/example/example.jam` (copied to `dist/example.jam`).

### Test

```bash
jammin test
```

Runs the AssemblyScript test suite for your service.

## Project Structure

```
.
├── jammin.build.yml
└── services/
    └── example/
        ├── asconfig.json
        ├── bin/
        │   └── test.js              # test harness runner
        ├── assembly/
        │   ├── index.ts             # exports { accumulate, refine }
        │   ├── service.ts           # your service logic
        │   ├── index.test.ts        # service tests
        │   ├── test-run.ts          # wires up test suites
        │   └── tsconfig.json
        └── package.json
```

## Editing your service

The entry point is `services/example/assembly/service.ts`. Export two functions:

- `accumulate(ptr: u32, len: u32): u64` — integrates work item results into state
- `refine(ptr: u32, len: u32): u64` — transforms work payloads into outputs

See the [as-lan documentation](https://todr.me/as-lan/) for the SDK reference and [more examples](https://github.com/tomusdrw/as-lan/tree/main/examples).

## Learn More

- [jammin docs](https://fluffylabs.dev/jammin/)
- [jammin on GitHub](https://github.com/FluffyLabs/jammin)
- [as-lan](https://github.com/tomusdrw/as-lan) — AssemblyScript SDK
- [@fluffylabs/as-lan on npm](https://www.npmjs.com/package/@fluffylabs/as-lan)
- [@fluffylabs/as-lan-ecalli-mocks on npm](https://www.npmjs.com/package/@fluffylabs/as-lan-ecalli-mocks)

## License

MPL-2.0
