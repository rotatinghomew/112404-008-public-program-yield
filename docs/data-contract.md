# 合成资料约定

资料用于本地业务流程演练，字段仅记录事实来源，不预先裁定业务结果。

- `activities.csv`：公众活动、场次、主题和预算事实。字段为 `activity_id, topic, slot_id, starts_at, ends_at, venue, capacity, fee, sponsor_seats, state`。
- `reservations.csv`：预约和候补状态。字段为 `reservation_id, activity_id, party_id, seats, access_need, created_at, state, notice_deadline`。
- `delivery_events.csv`：签到、取消、退款和反馈到达记录。字段为 `event_id, reservation_id, event_at, event_type, value, source`。
- `staff_and_rooms.csv`：讲解人员与场地时段安排。字段为 `resource_id, resource_type, slot_id, capacity, skill_or_access, state`。

空字段表示事实尚未提供，`pending`、`review`、`hold` 等状态表示来源记录尚未形成最终确认。不同来源以事件日期或有效期表达的时间含义不相同，调用方应结合表名和字段解释；不能仅因编号相同就假定两条记录可合并。金额以资料中记载的名义单位表示，没有统一换算或预先扣除退款。
