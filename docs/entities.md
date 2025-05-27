# Entites

- **Carrier**
    - carrierId , name
- **CellTower**
  - id, location , [connected carriers], [supported devices]
- **Device**
  - id, imei, userid, carrierId, osType
- **User**
    - userid, roleId, enterpriseid, ...
- **Role**
  - roleId, permissions
- **Enterprise**
  - enterpriseid, subscriptionplan
- **Policy**
  - policyid, enterpriseid, roleid, rules
- **Policy-Rule-outcomes**
  - ruleid, policyid, actionType(ex: upload, delete, message_send, photo), allow(true/false
- **Policy-Events**
  - eventid, time, deviceid, userid, appid, actionid, policyid, decision, towerid ... meta data.
