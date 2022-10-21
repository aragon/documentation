# Appeals - How much money is needed to appeal a dispute? And to confirm the appeal? What is it for?

* To appeal a dispute or confirm it, the amount required is `(Juror_Fee + Draft_Fee + Settle_Fee) x collateral factor x number of jurors`.
  * Guardian fees = `Juror_Fee`
  * Draft fees = `Draft_Fee`
  * Settlement fees = `Settle_Fee`
  * Collateral factor = 3 to appeal, 2 to confirm
* So that means:
  * Appeal dispute: `((Juror_Fee + Draft_Fee + Settle_Fee) x 3) x number of jurors`
  * Confirm appeal: `((Juror_Fee + Draft_Fee + Settle_Fee) x 2) x number of jurors`

| Appeal number | Number of guardians drafted |
| ------------- | --------------------------- |
| First appeal  | 9                           |
| Second appeal | 27                          |
| Third appeal  | 81                          |

* For the final round, the same formulas apply, but costs are reduced by 50%. The number of guardians for the final round is computed as `total active stake / min active balance`.
