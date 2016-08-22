# General Guidelines

This is a framework for writing `prompt` copy.

A user might uncover several prompts in the same session. Having those prompts feel like they were written by the same person is reassuring.

Any of these recommendations may by disregarded for the sake clarity. "MUST" rules will rarely find a good reason to be broken.

In most cases, this framework will get you to a passable prompt.

## Anatomy

* [Headline](#headline)
* [Body](#body)
* [Cancel Button](#cancel-button)
* [Continue Button](#continue-button)

## Color

* [Color Legand](#color-legand)

## Common Cases

* [Destroy Record](#destroy-record)
* [Discard State](#discard-state)
* [Disrupt Controlled Process](#disrupt-controlled-process)
* [Disrupt Uncontrolled Process](#disrupt-uncontrolled-process)

## Headline

* It **MUST** be present.
* It **MUST** be phrased as a question.
* It **SHOULD** be specific to the task.
* It **SHOULD** be answerable with "yes" or "no".
* It **MAY** be generic.

#### Good

> "Delete Person?"

> "Stop Mailing?"

> "Order Pizza?"

#### Poor but passable

> "Are you sure?"

#### Bad

> "Delete?"

> "Remove or keep?"

> "Cancel?"

## Body

* It **SHOULD** be present.
* It **SHOULD** clearly state the outcome of continuing.
* It **SHOULD** clearly state side effects.
* It **SHOULD** clearly state repeatability (if any).

#### Good

> "Deleting Cathy will remove her from People and all other Planning Center apps. Any related activity will also be deleted. You cannot un-delete Cathy."

> "Your registration is incomplete. Cancel now and your progress will not be lost."

> "Generating Lists can take up to 10 minutes. Your list might still be processing. If you cancel now, you can try again later."


#### Bad

> "You're about to take an action that cannot be undone."

> "Doing this may be dangerous."

> "Deleting this person has consiquences."

## Cancel Button

* It **MUST** be positioned left of the Continue Button.
* It **MUST NOT** be destructive.
* It **SHOULD** look safe/neutral (like hitting escape).
* It **SHOULD** read "Cancel" or be preceeded with "No, "
* It **MAY NOT** be present (if other close option is provided).

#### Good

> "Cancel"

> "Go back"

> "No, keep this person"

> "No, keep going" (when cancelling a kill-process request)

#### Bad

> "Yes"

> "Escape"

> "Undo"

## Continue Button

* It **MUST** be present.
* It **MUST** be positioned right of the Cancel Button.
* It's color **SHOULD** represent the action being taken.
* It **SHOULD** read "Continue" or preceeded with "Yes, "
* It **MAY** be destructive.

#### Good

> "Continue"

> "Keep going"

> "Yes, delete this person"

> "Yes, keep going"

#### Bad

> "No"

> "Enter"

## Color Legand

* CANCEL = `NO COLOR`
* DESTROY = `RED`
* CREATE = `GREEN`
* GENERIC, NON-GENERATIVE, NON-DESTRUCTIVE ACTION = `BLUE/GRAY`


## Destroy Record

A user shouldn't be able to easily delete data. Put some speed bumps in place.

Your first line of defence is going to be the Action button. It should look pretty ominous.

#### Action Button

The button should start with "Delete", "Remove", or the like. It should also be `red`.

```
+----------------+
|  Delete Cathy  |    <- It's red.
+----------------+
```

#### Prompt

##### Iteration 1

* Headline: generic
* Body: very specific. difficult to code.
* Cancel Button: "Cancel"
* Continue Button: "Yes, ..."

```
+-----------------------------------------------------------------+
|                          Are you sure?                          |
+-----------------------------------------------------------------+
|                                                                 |
|  Deleting Cathy will remove her from all Planning Center apps.  |
|     Her activity will be lost. You cannot un-delete Cathy.      |
|                                                                 |
|                               +---------------------+           |
|              Cancel           |  Yes, Delete Cathy  |           |
|                               +---------------------+           |
+-----------------------------------------------------------------+
```

##### Iteration 2

* Headline: specific
* Body: less specific. easy to code.
* Cancel Button: "No"
* Continue Button: "Yes, ..."

This is harder for the user to read but might spare some embarassing gender mishaps.

```
+-----------------------------------------------------------------+
|                          Delete Cathy?                          |
+-----------------------------------------------------------------+
|                                                                 |
|         Deleting this person will remove them from all          |
|   Planning Center apps. They're profile and activity will be    |
|           delted immediately. This can't be undone.             |
|                                                                 |
|                              +---------------------+            |
|                 No           |  Yes, Delete Cathy  |            |
|                              +---------------------+            |
+-----------------------------------------------------------------+
```

##### Iteration 3

* Headline: generic
* Body: less specific. easy to code.
* Cancel Button: "Cancel"
* Continue Button: "Yes, ..."

If the originating button clearly says what you'll be deleting, I'd probably land on this. Generic but contextually simple.

```
+-----------------------------------------------------------------+
|                          Are you sure?                          |
+-----------------------------------------------------------------+
|                                                                 |
|         Deleting this person will remove them from all          |
|   Planning Center apps. They're profile and activity will be    |
|           delted immediately. This can't be undone.             |
|                                                                 |
|                               +---------------------+           |
|              Cancel           |  Yes, Delete Cathy  |           |
|                               +---------------------+           |
+-----------------------------------------------------------------+
```

## Discard State

Discarding transient state isn't destructive. The user shouldn't feel too conserned about going back or exiting the process. But You'll see that it's really hard to write body text for.

The action button should look pretty safe. They shouldn't be afraid to back out of a process.

#### Action Button

The button read "Cancel", "Go back", "Leave", etc. It should NOT be `red`. `gray` or `no color` are appropriate.

```
+-----------------------+
|  Concel Registration  |    <- gray or no background color
+-----------------------+
```

#### Prompt

So the prompt is where you can find yourself in the "cancel my cancel" pit. Unfortunately, that doesn't leave us with a lot of options. The way out is to be explicit and *really* forc the "yes"/"no" respons.

* Cancel Button: "No, ..." (gray/no-color)
* Continue Button: "Yes, ..." (red)

```
+----------------------------------------------------------------+
|                        Cancel Registration?                    |
+----------------------------------------------------------------+
|                                                                |
|            You haven't completed your registration.            |
|         If you cancel now, your progress will be lost.         |
|                                                                |
|                               +----------------------------+   |
|      No, keep going           |  Yes, cancel registration  |   |
|                               +----------------------------+   |
+----------------------------------------------------------------+
```

## Disrupt Controlled Process

*Needs Graphic*

## Disrupt Uncontrolled Process

*Needs Graphic*
