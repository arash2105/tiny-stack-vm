# Tiny Stack VM

A faithful implementation of the tiny stack ISA v1 for the bounty.
`main.ts` runs every bytecode program in `/input/<id>/` with its
`input.bin` and writes `/output/<id>/stdout.bin` plus
`/output/<id>/exit.txt`.

It follows the reference VM (`generator/subject/vm.mjs`) exactly:
32-bit wrapping arithmetic, exact `Math.imul`, unsigned
`DIVU`/`MODU`/`LTU`, the `-2147483648 / -1` cases, 5-bit shift counts,
`PUSH8` sign extension, `EXIT`'s low byte, all ten traps with own
exit codes (2-11), step/output limits.

```sh
MAKEFUN_INPUT_DIR=practice/input MAKEFUN_OUTPUT_DIR=out node main.ts
```
