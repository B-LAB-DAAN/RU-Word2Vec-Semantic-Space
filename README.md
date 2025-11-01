# RU-Word2Vec-Semantic-Space: Low-Resource Russian NLP Vector Embeddings

## Обзор Проекта
Этот проект реализует тренировку **word2vec** моделей для русского языка в low-resource setup без использования крупных pretrained моделей (`HF`, `ruBERT`, `fastText`).  
Цель — показать способность строить семантическое пространство языка с нуля и выполнять семантический поиск / аналогии без heavy DL.

## Ключевые Результаты
* построено осмысленное русскоязычное semantic vector space  
* реализован semantic similarity + analogy retrieval pipeline  
* подходит для enterprise search / relevance / классификация / embeddings

## Архитектура и Технологии

### 1. Model
Используется классический **word2vec CBOW / Skip-Gram** (зависит от эксперимента) через `gensim` с кастомным preprocessing pipeline.

### 2. Semantic Retrieval
| Задача | Реализовано |
|--------|-------------|
| nearest neighbors | да |
| similarity scoring | да |
| analogy reasoning | да |
| возможность расширения на downstream задачи | да |

### 3. Входные Данные
На вход подаётся сырой текст на русском языке → токенизация → обучение word2vec → анализ семантики.

## Файлы Проекта
| Файл | Назначение |
|------|------------|
| `NLP1AS2.ipynb` | обучение word2vec + эксперименты semantic similarity / analogy |

(т.е. это целиком ноутбук проект, все эксперименты и inference уже внутри)

## Запуск проекта

### Требования

```bash
pip install numpy gensim
