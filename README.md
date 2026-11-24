# 公共艺术活动的候补释放与场次收益复盘

本项目保存视觉艺术机构日常业务分析使用的合成演练资料，样例不代表真实机构、作品、交易或研究结论。

## 资料

- `activities.csv`：公众活动、场次、主题和预算事实。字段为 `activity_id, topic, slot_id, starts_at, ends_at, venue, capacity, fee, sponsor_seats, state`。
- `reservations.csv`：预约和候补状态。字段为 `reservation_id, activity_id, party_id, seats, access_need, created_at, state, notice_deadline`。
- `delivery_events.csv`：签到、取消、退款和反馈到达记录。字段为 `event_id, reservation_id, event_at, event_type, value, source`。
- `staff_and_rooms.csv`：讲解人员与场地时段安排。字段为 `resource_id, resource_type, slot_id, capacity, skill_or_access, state`。

记录之间通过 `*_id`、`*_key` 或 `*_ref` 字段关联。日期采用 ISO 格式；空值表示来源未提供该事实，不代表数值为零。不同来源的统计范围和状态以 `docs/data-contract.md` 为准。样例中保留了待确认、取消、缺失和版本变化等原始情况，不包含预先计算的分析结论。

## 运行

需要 Python 3.11 或更高版本，无第三方依赖。运行 `python3 -m unittest discover -s tests -v` 可检查资料编码、字段和记录结构。
