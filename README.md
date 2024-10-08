![Python 3.6](https://img.shields.io/badge/python-3.6-green.svg)
## Описание
Обучить модель распознавать акт курения или табачную продукцию на изображении.

## Проблема
В тестовом датасете присутсвовали изображения, где акт курения или сигареты изображены ввиде картинок, были изображения, где табачная продукция изображена в очень маленьком размере. Нужно было достигнуть самой высокой точности по метрике accuracy.

## Решение
Для решения был создан и обработан собсвенный датасет на 40 тысяч изображений. Для обучения тестировались 3 модели: трансформер Swin, классификатор Yolo и детектор Yolo. К ним добавлялся последний слой и обучался на размеченом датасете. Лучший результат в наших тестах показал Swin, accuracy = 0.989


### Датасет

Датасет из 4000 изображений был изначально представлен организаторами. В ходе тестирования моделей были обнаружены категории изображений, которые прдесказывались хуже всего: нарисованные картинки и изображения людей с руками у лица без табачной продукции. Датасет был дополнен похожими картинками и в ходе работы дополнялся еще, пока не достиг 40000 изображений. Для Yolo был создан датасет в 20 тысяч фотографий, в котором акты курения и табачная продукция выделялась внутри изображения, разметка была создана с помощью roboflow.
