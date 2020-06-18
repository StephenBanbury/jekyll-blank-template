---
layout: post
title: Points Scoring
published: true
---

Keep it simple to start.

Then build complexity.

Initially I am thinking of earning a standard small number of points for each item assigned to a cause.

Gain a larger number of points for completing a deployment.

Gain points with respective funds raised

Lose some points for dropping an item on the floor.

Lose points for assigning to an incorrect scenario.

Lose points for assigning when you have already assigned the item to that scenario.

Lose points for going into the red.

Reset score to zero?

Lose arbitrary number of points.

Gain arbitrary number of points.

    public enum ScoreType
    {
        ResetScore = 0,
        LosePoints = 1,
        GainPoints = 2,
        ItemAssigned = 3,
        DeploymentCompleted = 4,
        FundsRaised = 5,
        ItemDropped = 6,
        IncorrectItemAssigned = 7,
        ItemAlreadyAssigned = 8,
        BalanceIntoRed = 9
    }