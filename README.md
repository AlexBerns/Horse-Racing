# Horse Race Prediction Project

This project aims to build and compare machine learning models capable of predicting the results of JRA horse races.

## JRA Data

We use the dataset `data.pkl` which contains 3 years worth of historical race data ranging from 2020/01/05 to 2022/12/28. We use the last 3 months for evaluation and the rest for training. Data format specifications and Code tables can be found in the `JV-Data490.xlsx` file.

A data entry consists of:

- Input with 224 features:
1: **raceid**: Race identifier  
2: **horseid**: Horse identifier  
3: **racedate**: Date of the race  
4: **futan**: Weight carried  
5: **umaban**: Horse number  
6: **wakuban**: Starting gate / barrier  
7: **blinker**: Blinkers equipped (0/1)  
8: **age**: Horse age  
9: **bataijyu**: Horse body weight  
10: **zogen**: Weight change since previous race  
11: **odds**: Betting odds  
12: **ninki**: Popularity rank (1 = most popular)  
13: **year**: Race year  
14: **sex**: Sex of the horse  
15: **KisyuCode**: Jockey code  
16: **TozaiCD**: East/West training center code  
17: **ChokyosiCode**: Trainer code  
18: **BanusiCode**: Owner code  
19: **jyo**: Racecourse code  
20: **kyori**: Distance (meters)  
21: **track**: Surface type (turf/dirt/etc.)  
22: **tenko**: Weather  
23: **baba**: Track condition  
24: **course**: Course layout (inner/outer, direction)  
25: **tosu**: Number of horses in the race  
26: **syubetu**: Race type/category  
27: **jyuryo**: Weight type  
28: **cls**: Class  
29: **grade**: Grade (G1/G2/G3/etc.)  
30: **BreederCode**: Breeder identifier  
31-220: same columns but from past races. _i means the value for the i-th race before this one.
221: **f**: Father's code  
222: **ff**: Father’s father's code  
223: **m**: Mother's code
224: **mf**: Mother’s father's code  

- Label:
The finishing position

- Harai / Payout: 
1. **RaceID**: Race identifier
2. **TorokuTosu**: Number of horses registered for the race.
3. **SyussoTosu**: Number of horses that actually started.
4. **FuseirituFlag**: Flags indicating invalid entries or non-starters (list of 9 flags).
5. **TokubaraiFlag**: Flags indicating special payout conditions.
6. **HenkanFlag**: Flags indicating refunded or void bets.
7. **HenkanUma**: List of horse numbers involved in refunds.
8. **HenkanWaku**: List of refunded bracket (waku) numbers.
9. **HenkanDoWaku**: List of refunded double-bracket combinations.
10. **PayTansyo**: Payouts for Win bets (単勝) — list of `{Umaban, Pay, Ninki}`.
11. **PayFukusyo**: Payouts for Place bets (複勝).
12. **PayWakuren**: Payouts for Bracket Quinella bets (枠連).
13. **PayUmaren**: Payouts for Quinella bets (馬連).
14. **PayWide**: Payouts for Wide / Place-Quinella bets (ワイド).
15. **PayReserved1**: Reserved field (unused but part of official JRA format).
16. **PayUmatan**: Payouts for Exacta bets (馬単, order matters).
17. **PaySanrenpuku**: Payouts for Trio bets (三連複).
18. **PaySanrentan**: Payouts for Trifecta bets (三連単).
19. **Year**: Year of the race.
20. **MonthDay**: Month and day of the race (MMDD).
21. **JyoCD**: Racecourse code.
22. **Kaiji**: Meeting number (開催).
23. **Nichiji**: Day number within the meeting.
24. **RaceNum**: Race number of the day (1–12).

## Metric

We want to predict the finishing positions of each horse, and maximise the payout.

## Models

We implemented diffrent machine learning models:
- LightGBM

## Results

