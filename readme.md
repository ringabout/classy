# Classy

[![Software License][ico-license]](license.md)
![Stability][ico-stability]

Haskell-style typeclasses for Nim.

Allows to instantiate collections of functions for a given type or type constructor.

## Install

```bash
$ nimble install classy
```

## Usage

```nim
import classy

typeclass Functor, F:
  # proc map[A, B](fa: F[A], g: A -> B): F[B]
  proc `$>`[A, B](fa: F[A], b: B): F[B] =
    fa.map((a: A) => g)

instance Functor, seq[_]
assert: (@[1, 2, 3] $> "a") == @["a", "a", "a"]
```
## Documentation

Upcoming. For the moment please refer to [example](example.nim) for more in-depth explanation.

## Testing

```bash
$ nimble tests
```

## Stability

Highly experimental. API and behaviour subject to change.

## Credits

- [:nigredo-tori][nigredo-tori]

## License

The Unlicense. Please see [License File](license.md) for more information.

[ico-license]: https://img.shields.io/badge/license-Unlicense-brightgreen.svg?style=flat-square
[ico-stability]: https://img.shields.io/badge/stability-experimental-orange.svg?style=flat-square