# Short Responses

For this short response assignment, aim to write a response with the following
qualities (your instructor will give you feedback on these areas):

- [ ] Addresses all parts of the prompt
- [ ] Accurately uses relevant technical terminology
- [ ] Is free of grammar and spelling mistakes (double check with Grammarly!)
- [ ] Uses markdown to enhance readability (preview in VS Code with
      Command/Control + Shift + V)
- [ ] Is easy to comprehend

Write your response in the space provided. Make sure to preview your markdown
to check how it is rendered before submitting.

## Question 1

Here is a `Member` class as it stands today. Every attribute is public.

```py
class Member:
    def __init__(self, name, email, joined_on, bikes_out):
        self.name = name              # "Ana Reyes"
        self.email = email            # "ana@example.com"
        self.joined_on = joined_on    # "2026-03-14", never changes after signup
        self.bikes_out = bikes_out    # 2, goes up and down all day
```

For **each of the four**, say whether you would leave it public or make it
non-public with a single leading underscore, and give your reason in one
sentence. A reason that is only "it feels internal" is not a reason — say what
would go wrong, or what would not.

Then answer this: for whichever ones you made non-public, what has actually
changed? Another programmer can still write `member._bikes_out = 99` and Python
will let them. So what does the underscore accomplish, and what does it not
prevent?

### Your Response

[Write your response here]

## Question 2

Three engineers each propose a new class for Boro Bikes. All three reach for
inheritance.

```py
class Dock(Station):          # a single dock at a station
class CargoBike(Bike):        # a bike with a crate on the front
class Invoice(Member):        # a month's charges for one member
```

For each one, say whether inheritance is right. Use the phrases **"is a"** and
**"has a"** to explain each answer: ask whether the new class is a kind of the
class in parentheses, or whether one of the two classes should hold the other.
Where inheritance is wrong, name the class that should hold the other.

Then, for the one proposal that is a case for inheritance, name one method or
attribute it would receive from its parent that it would otherwise have to
write again.

### Your Response

[Write your response here]

## Question 3

Python finds an attribute by looking in a fixed order: the instance first, then
its class, then the parent class, then `object`, and it stops at the first
place it finds the name. That search is the whole mechanism behind a subclass replacing a parent's
method.

```py
class Bike:
    BASE_RATE = 3.00

    def __init__(self, serial):
        self.serial = serial

    def hourly_rate(self):
        return Bike.BASE_RATE


class ElectricBike(Bike):
    def __init__(self, serial, battery_range):
        super().__init__(serial)
        self.battery_range = battery_range


electric = ElectricBike("E9", battery_range=24)
```

A teammate wants to give the rider of `electric` one free ride, and runs these
lines:

```py
electric.BASE_RATE = 0
print(electric.BASE_RATE)       # 0
print(electric.hourly_rate())   # 3.0
```

The first `print()` shows `0`, but the second still shows `3.0`. For each
`print()`, say where Python finds `BASE_RATE`: name each place it looks, in
order, and the place it stops. Then explain why the free ride did not happen. Then say what the teammate would have to write to change the rate
that `hourly_rate()` returns, and what that line would do to every other bike.

### Your Response

[Write your response here]
