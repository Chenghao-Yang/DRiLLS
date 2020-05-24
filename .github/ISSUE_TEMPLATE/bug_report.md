---
name: Bug report
about: Create a report to help DRiLLS improve
labels: 
---

**Describe the bug**
RuntimeError: tf.placeholder() is not compatible with eager execution.

**To Reproduce**
run python drills.py train scl  in ubuntu16.04
4. [DRiLLS 2020-05-24 19:18:36] Starting to train the agent ..
2020-05-24 19:18:36.433443: I tensorflow/core/platform/cpu_feature_guard.cc:142] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
2020-05-24 19:18:36.457176: I tensorflow/core/platform/profile_utils/cpu_utils.cc:94] CPU Frequency: 2199995000 Hz
2020-05-24 19:18:36.458000: I tensorflow/compiler/xla/service/service.cc:168] XLA service 0x55e83924b370 executing computations on platform Host. Devices:
2020-05-24 19:18:36.458038: I tensorflow/compiler/xla/service/service.cc:175]   StreamExecutor device (0): Host, Default Version
Traceback (most recent call last):
  File "drills.py", line 64, in <module>
    learner = A2C(options, load_model=args.load_model, fpga_mapping=fpga_mapping)
  File "/home/yangch/Logic/Reinforcement/drills/model.py", line 55, in __init__
    self.state_input = tf.placeholder(tf.float32, [None, self.state_size])
  File "/home/yangch/.tensor/lib/python3.6/site-packages/tensorflow_core/python/ops/array_ops.py", line 2627, in placeholder
    raise RuntimeError("tf.placeholder() is not compatible with "
RuntimeError: tf.placeholder() is not compatible with eager execution.


**Expected behavior**
I want to solve this bug，thank you very much

**Additional context**
  File "/home/yangch/.tensor/lib/python3.6/site-packages/tensorflow_core/python/ops/array_ops.py", line 2627, in placeholder
    raise RuntimeError("tf.placeholder() is not compatible with "
RuntimeError: tf.placeholder() is not compatible with eager execution.
