# TF_learning-Tensorboard
Tensorboard 可以图形化你的TF过程，包括有loss值，acc值等，还具有图形化张量训练的过程。

但是 Tensorboard 的官方文档说明较为复杂而且乱，本文档仅做最简单使用的说明。
# 运行环境
tensorflow --2.6.0

python     --3.9.17
# Tensorboard  API
Tensorboard(log_dir="./logs", histogram_freq=0, write_graph=Ture,  write_grads=False, write_images=False, update_freq='epoch' )

括号内均为默认值

log_dir : 保存所需文件地址，默认为./logs，建议自行编码一个特别记录目录，以免多次训练数据混乱。

histogram_freq： 对模型中各个层的采样频率，关系到激活值和权重直方图。

write_graph： 是否可视化图形。

write_grads:  是否采集展示直方图。

batch_size:   训练模型难道不设置这个嘛？ pass

write_images : 是否模型权重可视化。

update_freq :  可选batch、epoch、整数。在（可选内容）之后进行训练数据采集。
# code--tf1
log_dir = "logs_date/" + datetime.datetime.now().strftime("%m-%d--%H%M%S")

log_dir 设置存贮位置及名称 

tensorboard_callback = tf.compat.v1.keras.callbacks.TensorBoard(log_dir=log_dir, histogram_freq=1, write_grads=True)

无需导入Tensorboard 模块
