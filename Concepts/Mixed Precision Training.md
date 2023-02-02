A way to speed up Machine Learning Training without losing accuracy.

As was being discussed within [[Google TPU]], [[Machine Learning]] research has found that despite lowering the precision of some calculations, you can still end up with the same amount of accuracy.
No task specific accuracy is lost through identifying which steps require a full precision float32 and using lower precision elsewhere.

==mixed precision training== uses operations of lower precision (float16, [[Floating Point Numbers#^d049d7|bfloat16]]) in a model to:
- use less memory
- run faster