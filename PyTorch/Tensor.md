---
type: concept
area: PyTorch
status: learned
created: 2026-06-26
updated: 2026-06-27
tags:
  - pytorch
  - tensor
  - array
confidence: 0.90
---

# Tensor

Tensor — основной объект PyTorch. Практически любые данные перед обучением модели представлены в виде Tensor: изображения, текстовые embeddings, аудио, таблицы, параметры модели и промежуточные активации.

## Простое объяснение

Tensor — это многомерный массив, который умеет быстро выполнять вычисления и является базовым типом данных PyTorch.

Его удобно представить как универсальный контейнер данных для нейросетей: он похож на NumPy array, но дополнительно поддерживает GPU, `device`, `dtype` и автоматическое дифференцирование через [[Autograd]].

## Зачем это нужно

- Tensor используется абсолютно во всех моделях PyTorch.
- Без Tensor невозможно нормально работать с [[Dataset]], [[DataLoader]], слоями сети и обучением моделей.
- Tensor хранит входные данные, веса, bias, logits, loss и градиенты.

## Как это работает

Tensor может иметь любое количество размерностей:

- scalar — 0D Tensor;
- vector — 1D Tensor;
- matrix — 2D Tensor;
- batch изображений — часто 4D Tensor вида `(batch, channels, height, width)`.

Главная идея: не думать о Tensor как об обычном Python list. List хранит элементы, а Tensor хранит числовую структуру, над которой PyTorch умеет делать быстрые операции.

## Пример

```python
import torch

x = torch.tensor([1, 2, 3])
y = torch.tensor([
    [1.0, 2.0],
    [3.0, 4.0],
])

print(x.shape)   # torch.Size([3])
print(y.shape)   # torch.Size([2, 2])
print(y.dtype)   # torch.float32
print(y.device)  # cpu
```

## Типичные ошибки

- Представлять Tensor как обычный Python list.
- Не понимать, что Tensor используется для хранения реальных данных модели.
- Путать Tensor с NumPy array и забывать про `device`.
- Делать операции между Tensor разного `dtype` или на разных устройствах.

## Связанные темы

[[Shape]] · [[Tensor Dimensions (ndim)]] · [[Tensor Creation]] · [[Tensor Dtype]] · [[Broadcasting]] · [[Autograd]]
