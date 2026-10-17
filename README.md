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
The interface is simple. There is one main screen with three areas.

Members and balances. A list shows every member in the group with a balance next to their name. A positive balance (shown in green) means the group owes that member money. A negative balance (shown in red) means the member owes the group. A zero balance is shown in gray. Players can add a member by typing a name and tapping the add button. A member cannot be removed while their balance is nonzero, and names must be unique within the group.

Expense log. Below the member list, a scrollable list shows all recorded expenses from newest to oldest. Each row shows the description, amount, payer, and participants. Selecting a row and tapping delete removes the expense and updates all balances immediately.

Add expense form. The user enters a description and an amount, picks a payer from a drop-down menu, and checks the participants who share the cost. Each checked participant has a weight field that defaults to 1. A participant with weight 2 pays twice as much as a participant with weight 1, which is useful when someone ate more, stayed longer, or is covering a partner. The share for each participant is their weight divided by the total weight, multiplied by the amount. Tapping the add button records the expense. The button is disabled until the description is not empty, the amount is greater than zero, a payer is chosen, and at least one participant is checked.

Amounts are stored in whole cents to avoid rounding errors. When a split does not divide evenly, the leftover cents are assigned one at a time to participants in the order they appear in the member list, so the shares always add up exactly to the total.

After an expense is added, the form clears and the balances update. If the payer is also a participant, their own share is not counted as a debt to themselves.

Settle up screen. Tapping the settle up button opens a second screen that lists the smallest practical set of payments needed to bring every balance to zero (for example, “Priya pays Sam $12.50”). The app generates this list by repeatedly matching the member who owes the most with the member who is owed the most. Next to each suggested payment is a mark-as-paid button, which records the payment as a transfer between those two members and updates their balances. When all balances reach zero, the screen shows an “All settled up” message.

The app saves the group, expenses, and payments to a local file when any change is made and loads them when the app starts, so nothing is lost when the app closes. A reset button on the main screen clears the entire history, after asking the user to confirm.


