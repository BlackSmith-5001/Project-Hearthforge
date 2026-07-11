# What is JSON?

JSON is not something you need to program.

For PIM-DBS, you can think of JSON as a **structured notebook** that an AI can read clearly.

For example:

```json
"Name": "Luna"
```

means:

```text
The name is Luna.
```

---

## The main rule

In the PIM-DBS template, you can usually replace only the text inside `< >`.

Example:

```json
"Name": "<The name you want to give to the AI>"
```

You can change it to:

```json
"Name": "Luna"
```

---

## Symbols you should not delete casually

These symbols hold the JSON shape together:

```text
{ }
[ ]
"
,
:
```

If you are not sure what they do, leave them in place.

---

## Common mistakes

### 1. Removing quotation marks

Broken:

```json
"Name": Luna
```

Safer:

```json
"Name": "Luna"
```

Most text should stay inside quotation marks.

---

### 2. Removing commas

Broken:

```json
"Name": "Luna"
"Callsign": "Night-sky companion"
```

Safer:

```json
"Name": "Luna",
"Callsign": "Night-sky companion"
```

---

### 3. Writing comments inside JSON

Broken:

```json
"Name": "Luna" <- write the name here
```

Safer:

```json
"Name": "Luna"
```

If you need notes, put them inside a field such as `Notes`.

---

## Fields you may edit

Replace placeholder text like this:

```json
"Style": "<Tone and Personality Settings>"
```

with your own words:

```json
"Style": "gentle, calm, and slightly playful"
```

---

## Unknown fields can stay unknown

You do not have to fill in every field.

Example:

```json
"Origin": "<not specified>"
```

Do not ask the AI to invent real private history, personal details, or memories that were not provided.

---

## If the JSON breaks

Ask an AI:

```text
Please repair this JSON without adding new content.
Keep unknown fields as <not specified>.
Do not invent missing details.
```

---

## Before publishing anything

Check that the profile does not contain:

- real names
- addresses or locations
- school, workplace, or organization names
- medical, family, financial, or legal context
- real conversation logs
- screenshots
- other people's private stories

When in doubt, keep it private.

---

## Final note

JSON is just a notebook with a strict shape.

Keep the shape intact, replace only the words you understand, and save private profiles locally.
