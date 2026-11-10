---
layout: default
title: Home
---

# DSC 180A — Methodology Assignment 4

**Emily Yip** · [emyip@ucsd.edu](mailto:emyip@ucsd.edu)

Section: D11 · Mentor: Mark Dixon

---

## Quarter 2 Project brainstorm

**What is the most interesting topic covered in your domain this quarter?**

The thing that stuck with me most was realizing how much fire risk comes down to how dry the air is, not just how much it rains. For my Q1 project I calculate vapor pressure deficit (VPD) for every grid cell in Spain and Portugal each month. It's basically a measure of how thirsty the air is: when VPD is high, the atmosphere pulls moisture straight out of the plants, so they dry out and burn more easily even if the area got rain recently. I went in assuming rainfall would be the main driver, so seeing dryness matter this much changed how I think about the whole problem.

**Describe a potential investigation you would like to pursue for your Quarter 2 Project.**

For Q2 I'd like to go from predicting whether a cell burns in a given month to predicting how early you can actually see that risk coming. I'd build features from earlier months (VPD, rainfall, and a drought index from one, three, and six months before) and check how far ahead those start to separate the fire months from the normal ones. If you can tell a cell is at risk two or three months out, that's a lot more useful than only knowing the same month it burns, since a fire agency could actually act on that kind of warning. I'd test it with year-based splits and be upfront about how much the prediction weakens the further ahead I try to look.

**What is a potential change you'd make to the approach taken in your current Quarter 1 Project?**

The main thing I'd change is the monthly resolution. Most fires start and end within a few days, so squishing a whole month into one row kind of washes out the short dry spells that actually set them off. You could have a really hot, dry two weeks get cancelled out by rain earlier in the same month and never see it in the data. Next quarter I'd try building the weather features weekly, or even daily, so the model can pick up those short extremes. I'd also want to revisit how I compute VPD. Right now I use a quicker version based on daily max temperature and daily average dewpoint, which gets the ranking between cells right but underestimates the real afternoon peak, so I'm curious whether switching to hourly data actually changes the results.

**What other techniques would you be interested in using in your project?**

There are a few things I'd want to try:

- Splitting the data by region instead of just by year, so I can tell whether the model actually works in places it's never seen, not just in new years.
- Using SHAP to see which features drive each prediction, mostly as a sanity check that it's leaning on things like dryness and not just memorizing location or season.
- Calibrating the probabilities (something like Platt scaling or isotonic regression), because for a fire model a "10% chance" really needs to mean 10%, not just rank cells in the right order.
- If I have time, trying something like a ConvLSTM that handles space and time together, since the data is basically a grid changing over time and a per-cell model probably misses the bigger patterns.

---

<sub>Built with Jekyll and GitHub Pages · theme: cayman</sub>
