# Breaking

*This challenge was removed due to the flag being set incorrectly on the CTF platform.*

We are presented with a chess FEN list, resembling the match between Ian Nepomniachtchi and Ding Liren

The FEN Lines had 16 anomalies, invalid FEN lines:

1. white instead of black (w -> b)
2. knight instead of rook (n -> r)
3. 4 -> 3 (9 total columns on the 5th rank dont make sense)
4. In the 50 Move rule column is a  "4" instead of the "2"
5. The king is missing ("K"), only 7 columns on the 1st Rank: RB1Q1R1 -> RB1Q1RK1
6. 59 Move rule column was set to 0 but needs to be 1
7. Here is a bishop instead of a queen ("b" -> "q")
8. A "k" is in the castling column ("k" -> "-")
9. Here is a "N" instead of an "K" ("N" -> "K")
10. 2 -> 1 (9 total columns on the 4th rank dont make sense)
11. 3 -> 2 (9 total columns on the 5th rank dont make sense)
12. a p is missing and got replaced by a 1 (5rq1 -> 5rqp)
13. A "Q" is in the castling column ("Q" -> "-")
14. Here is a "N" instead of an "B" ("N" -> "B")
15. 2 -> 1 (9 total columns on the 4th rank dont make sense)
16. instead of "f3" there is a "g3" on the en passant column

Combining all the anomalies gives us:
br32K1q-K12p-B1f, simply put it in the [flag format](https://github.com/QWERTZexe/THAINNOS-hacking-challenge-2026-writeup/blob/main/README.md) and you would have solved breaking!