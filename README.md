# Project Brief: The "Last Mile" Logistics Auditor

---
## A. Executive Summary

Looked at around 99,000 orders from Olist, a Brazilian e-commerce platform, to figure out where deliveries were going wrong and whether customers actually noticed. About 8% of orders arrived late, and the states hit hardest were up in the northeast — places like AL and MA that are just far from where most of the stock sits (São Paulo). It also showed up in the reviews: orders that arrived on time averaged 4.29 stars, while late ones dropped to 3.46. And when I dug into the seller data, some vendors had late rates above 50%, which tells me this isn't just a logistics problem — some sellers are consistently underperforming.

---

## B. Project Links

- **Notebook:** [Google Colab Link](https://colab.research.google.com/drive/18Fs4J6lfgTIlrJDvjsay53tEY-DbZK6Z?usp=sharing)
- **Dashboard:** 
- **Presentation:** [Slide deck](https://docs.google.com/presentation/d/1VTgyQm3h6-ll_PxVNjLaunDLindBGRVu/edit?usp=drive_link&ouid=108888480646218539322&rtpof=true&sd=true)

---

## C. Technical Explanation

### Data Cleaning

The data came in 6 separate files, so the first job was joining them into something usable. The tricky part was the reviews table — some orders had more than one review, and if I'd joined it directly it would've created duplicate rows and messed up the whole dataset. So I averaged the scores per order first, then merged. I also had to convert the date columns from plain strings into actual datetime format before I could do any math on them. For orders that were canceled or still in transit, I didn't just drop them — I gave them their own category so they wouldn't quietly skew the late delivery numbers.
