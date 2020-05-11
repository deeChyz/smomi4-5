# smomi4-5


'' 4 lab ''

а) Аугментация с использованием отражения:

Способ и параметры: '' tf.image.random_flip_left_right(image) ''

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/1stStage/res.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/1stStage/train.py


б) Агументация с помощью поворота на случайный угол:

Способ и параметры: '' image = tf.contrib.image.rotate(image, dgr * math.pi / 180, interpolation='BILINEAR') ''

'20 градусов' 

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/2ndStage/resA.jpg)


'50 градусов' 

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/2ndStage/resB.jpg)


'40 градусов' + resize

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/2ndStage/resC.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/2ndStage/train.py


с) Аугментация с помощью случайного изменения яркости:

Способ и параметры: '' tf.image.random_brightness(image, 0.6, seed=None)
        tf.image.random_contrast(image, lower=0.2, upper=1.2 seed=None) ''

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/3rdStage/resA.jpg)


Способ и параметры: '' tf.image.random_brightness(image, 0.35, seed=None)
        tf.image.random_contrast(image, lower=0.2, upper=1.2 seed=None) ''


![Image description](https://github.com/deeChyz/smomi4-5/blob/master/3rdStage/resB.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/3rdStage/train.py


d) Аугментация с помощью вырезки случайного участва изображения:

Способ и параметры: '' tf.image.random_crop(image, size=[112, 168, 3], seed=None, name=None) ''

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/4thStage/resA.jpg)

Способ и параметры: '' tf.image.random_crop(image, size=[168, 168, 3], seed=None, name=None) ''

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/4thStage/resB.jpg)


Способ и параметры: '' tf.image.random_crop(image, size=[168, 168, 3], seed=None, name=None) & .map(resize)'' 

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/4thStage/resC.jpg)


Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/4thStage/train.py



e) Итоговая аугментация со всеми способоами и оптимальынми параметрами:

Способ и параметры: '' 
image = tf.image.random_crop(image, size=[168, 168, 3], seed=None, name=None)
image = tf.image.random_flip_left_right(image)
image = tf.image.random_brightness(image, 0.35, seed=None)
image = tf.image.random_contrast(image, lower=0.2, upper=1.2, seed=None)
degree = 60
dgr = random.uniform(-degree, degree)
image = tf.contrib.image.rotate(image, dgr * math.pi / 180, interpolation='BILINEAR')
''

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5thStage/res.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/5thStage/train.py




'' Lab 5 ''

a) Пошаговое затухание


![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/1stage.jpg)

With edited initial model

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/1stageB.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/5thStage/1stage.py

b) Экспоненциальное затухание


![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/2stage.jpg)

With edited initial model

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/2stageB.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/5thStage/2stage.py

c) Разогрев + пошаговое затухание


![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/3stage.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/5thStage/3stage.py

d) Разогрев + экспонинциальное затухание


![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/4stage.jpg)

With edited initial model

![Image description](https://github.com/deeChyz/smomi4-5/blob/master/5lab/4stageB.jpg)

Ссылка на код: https://github.com/deeChyz/smomi4-5/blob/master/5thStage/4stage.py
