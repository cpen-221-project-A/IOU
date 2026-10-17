# IOU

## Team Members
- Garvit Bhasin
- Rory Cong
- Nik Kos
- Tyler Tuo
- Eason Xu

## Mission Statement
Making budgeting easier.

## Problem Statement
People who live with roommates or share costs often have trouble keeping track of who paid what and how much each person should pay. Costs like groceries, rent and electricity might be paid by people and split in different ways. Some costs might only apply to one person while others are shared by everyone. Keeping track of all these things by hand can take a lot of time and can lead to confusion.

Current methods like spreadsheets and messaging apps usually make people do the math themselves and figure out who owes what. There is a need for a tool that brings all shared expenses together allows for different ways to split costs and works out the balances automatically.

## Solution Statement
We propose a Shared Expense Splitter, a Java application that allows groups to record shared expenses, calculate individual contributions, adjust weights, and track outstanding debts.

A group is a named list of members, such as housemates on a trip or a dinner party. Any member can pay for an expense on behalf of the group. Each expense has a description, an amount in dollars and cents, a payer, and a set of participants who share the cost. By default, an expense is split equally among its participants. The app then keeps a running balance for each member, so everyone can see who owes money and who is owed.
