- Power Station = J
- Relay Tower = R
- Transponder = T
- User Device(s) = D1,D2,D3...

---

Operations: Send Following Signal > | Position Check ^ | Drop Connection v

---

Signal Codes:
- Device Radius Signal: S
- Okay To Proceed: C
- Close Connection: X
- Device Check: F
- Battery Check: B
- Power Level: P+=() or P-=() Use Power Codes for reference
- Distribute: E

Battery Levels:
- Need: 0
- Stop: 1

Power Codes:
- A(#####) Milli Amp Hour ((mAh)*(V)/1000 = (Wh))
  - YA: Safe Constant
- W(#####) Watt Hour ((Wh)*(1000) = (GWh))
  - YW: Safe Constant
- G(#####) GigaWatt Hour (Warning - High Output)
  - YG: Safe Constant

---
Mock Example
```
1) D#S > TF
  2) TF ^ D1B
    3) 0 > D1C > P+=A(1047)
  2) TF ^ D2B 
    3) 1 v D2X
  2) TF ^ D3B 
    3) 1 v D3X
  2) TF ^ D4B 
    3) 0 > D4C > P+=W(470)
  2) TF ^ D5B 
    3) 0 > D5C > P+=W(37)
4) TC > RC > JC 
5) (Interval Submit Output 6+)
6) JC > RC > TE
  7) D1E > P-=(A(1047)-YA) > D1B > 1 v D1X
  7) D4E > P-=(W(470)-YW) > D4B > 0 > D4C
  7) D5E > P-=(W(37)-YW) > D5B > 1 v D5X
    8) {P>=0} > TE | TX
      9) D4E > P-=(W(170)-YW) > D4B > 1 v D4X
        10) {P>=0} > TE | TX
11) (Connection Closed)
```
