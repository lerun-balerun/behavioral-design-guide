# Мини-ревалидация v1.3 — EarnUp + Mumbai

**Цель:** проверить, что три v1.3 фикса (Route A gate, Ethical mirror/Risk compensation, Miscalibrated Beliefs + Zeigarnik) действительно закрывают дыры, которые провалились на v1.2.

**Два кейса:** Case 06 EarnUp (v1.2: 16/30) и Case 07 Mumbai (v1.2: 17/30).

**Ожидания:**
- **EarnUp** должен подняться до 22-25/30. Route A gate должен поймать rounding pattern в данных. Если поднялся < 20 — фикс не работает как задумано.
- **Mumbai** должен подняться до 20-24/30. Perceptual miscalibration теперь явная категория в DIAGNOSE. Risk compensation теперь явный checkpoint в OPTIMIZE. Но Mumbai сложный — поднятие до 22+ будет достаточно, до 25+ было бы excellent.

**Сколько времени:** ~30-40 минут Cursor'а.

---

## Шаг 1. Solver (один чат на оба кейса)

1. Новый чат в Cursor. Модель: **Claude Sonnet 4.6**.
2. Прикрепи файлы:
   - `SKILL.md` (теперь v1.3, обновлён)
   - `validation/validation_cases.md`
3. Скопируй solver prompt из `validation/solver_prompt.md` — блок от `You are going to act as the Behavioral Design Guide skill...` до `Explicitly say "Starting Case NN from scratch" at the top of each run.`
4. Вставь первым сообщением. Отправь.
5. Когда Cursor готов:
   - Напиши: `run case 06` → дождись файла `validation/runs/case_06_run.md` (будет перезаписан)
   - Напиши: `run case 07` → дождись `validation/runs/case_07_run.md`
6. Закрой чат.

**Важно:** старые файлы `case_06_run.md` и `case_07_run.md` с v1.2-прогонов будут перезаписаны. Если хочешь сохранить их для сравнения — заранее скопируй в `validation/runs/v1.2_archive/case_06_run.md` и т.д.

## Шаг 2. Evaluator (один чат на оба кейса)

1. **Новый** чат, отдельно от solver-чата. Модель: Claude Sonnet 4.6.
2. Прикрепи файлы:
   - `validation/validation_ground_truth.md`
   - `validation/validation_rubric.md`
   - `validation/runs/case_06_run.md` (новый)
   - `validation/runs/case_07_run.md` (новый)
3. **НЕ** прикрепляй SKILL.md.
4. Скопируй evaluator prompt из `validation/evaluator_prompt.md` — блок от `You are an independent evaluator...` до конца per-case output format.
5. Вставь. Отправь.
6. Когда готов:
   - Напиши: `evaluate case 06` → дождись файла (перезапишет старый)
   - Напиши: `evaluate case 07` → дождись файла
7. Закрой чат.

## Шаг 3. Читаем результаты

Открой два eval-файла. Сравни с v1.2:

| Кейс | v1.2 | v1.3 цель | v1.3 факт | Фикс сработал? |
|---|---|---|---|---|
| 06 EarnUp | 16 | 22-25 | ? | ? |
| 07 Mumbai | 17 | 20-24 | ? | ? |

**Что означают результаты:**

- **EarnUp 22+:** Route A gate работает. Публикуемся.
- **EarnUp 18-21:** Фикс частично работает — Route A gate замечен, но Round Up framing всё ещё не возникает. Это значит проблема не только в routing, но и в отсутствии round-number technique в Table D. Минорная правка — добавить Round Up / Mental Accounting в таблицу техник.
- **EarnUp <18:** Фикс не работает. Остановись, пиши мне, разберёмся.

- **Mumbai 20+:** Оба фикса работают. Публикуемся.
- **Mumbai 17-19:** Perceptual miscalibration упомянута, но не приводит к правильному интервенционному решению. Это архитектурная граница скилла — фикс подсветил проблему, но не полностью её решил. Приемлемо для v1.3 beta.
- **Mumbai <17:** Регресс. Что-то сломалось. Пиши мне.

---

## После ревалидации

- Обнови `VALIDATION_SUMMARY.md` — добавь секцию «v1.3 re-validation» с новыми оценками и кратким комментарием.
- Или создай отдельный `VALIDATION_SUMMARY_v1.3.md` и оставь оригинальный как есть. Что тебе удобнее.

Затем возвращайся ко мне — пойдём к README + publication posts.
