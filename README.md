# lambda
Notes on "An introduction to functional programming through lambda calculus"

```
identity      = λx.x
self_apply    = λx.(x x)
apply         = λx.λy(x y)
select_first  = λx.λy.x
select_second = λx.λy.λy = λx.identity
make_pair     = λx.λy.λz.((z x) y)

(((make_pair identity) apply) select_first)  = identity
(((make_pair identity) apply) select_second) = apply
```
