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
will let them. So what did the underscore buy, and what did it not?

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

For each one, say whether inheritance is right, and if it is not, what the class
should hold instead. Use the phrases **"is a"** and **"has a"** in your answer
and make them do real work — `Dock` is a dock, not a station, so what is the
relationship?

Then answer this: one of the three is genuinely a case for inheritance. Say
which, and name one thing it would get from its parent for free that it would
otherwise have to write again.

### Your Response

[Write your response here]

## Question 3

This question asks you to **write test code**, not prose. You will do the same
thing in the project, where requirement 9 asks you to prove a refusal.

Here is a validating setter. Assume it works.

```py
class Station:
    def __init__(self, name, capacity):
        self.name = name
        self.capacity = capacity

    @property
    def capacity(self):
        return self._capacity

    @capacity.setter
    def capacity(self, value):
        if value < 1:
            raise ValueError("A station needs at least one dock.")
        self._capacity = value
```

Write **two** tests for it. Use `src/playground.py` in the code repo to actually
run them, then paste them here.

1. A test that proves the setter refuses a capacity below 1. Use
   `pytest.raises(ValueError)`.
2. A test that proves the stored value is unchanged after that refusal.

Then, under each test, write one sentence saying **what that test would catch**
— the specific broken version of the setter that passes the other test and
fails this one.

The second part is the question. Two tests that cannot fail differently are one
test written twice, and the sentence is how you find that out.

### Your Response

[Write your response here]

