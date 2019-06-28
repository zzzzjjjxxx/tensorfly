# tensorfly
有一段很短的python程序生成了一些三维数据，然后用一个平面拟合它
import tensorFlow as tf
import numpy as np

# 使用numpy生成假数据，总共100个点
X_data = np.float(np.random.rand(2, 100)) 随即输入
y_data = np.dot([0.100, 0.200], x_data)+0.3

#构造一个线性模型
b= tf.Variable(ti.zeros[1])
w = tf.Variable(tf.random_uniform([1, 2], -1.0, 1.0))
y = tf.matmul(w, x_data)+b

# 最小化方差
loss = tf.reduce_mean(tf.square(y-y_data))
optimizer = tf.train.GradientDescentOptimizer(0.5)
train = optimizer.minimize
# 初始化变量
init = tf.initialize_all_variables()
#启动图
sess = tf.Session()
sess.run(init)
# 拟合平面
for step in xrange(0, 201):
sess.run(train)
if step% 20 == 0:
  print step,sess.run(W),sess.run(b)
#得到最佳拟合结果 w：[[0.100 0.200]], b: [0.300]
