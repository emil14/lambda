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

true  = select_first
false = select_second
cond  = make_pair
not   = λx.(((cond false) true) x) -> λx.((x false) true)
and   = λx.λy.(((cond true) y) x)

zero = λx.x = identity
succ = λn.λs.((s false) n)
pred = λn.(n select_second)

one   = (succ zero) = λs.((s false) λ.x.x)
two   = (succ one)  = λs.((s false) λs.((s false) λ.x.x))
three = (succ two)  = λs.((s false) λs.((s false) λs.((s false) λ.x.x)))

is_zero = λn.(n select_first)
```
