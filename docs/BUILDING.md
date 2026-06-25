# Building A Career Coach

## 1. Define The Job

A career coach should help a user make better career decisions in a specific context. Start by choosing the target scope:

- Function: product, engineering, design, sales, marketing, research, operations
- Seniority: early career, mid-level, senior IC, manager, executive
- Market: local, regional, global, startup, big company, regulated industry
- Main use cases: review, interview practice, positioning, negotiation, learning plan

Avoid building a generic "career advice" bot. Generic advice is easy to generate and hard to trust.

## 2. Split Context Into Layers

Use four layers:

| Layer | Example Content | Commit To Public Repo? |
|---|---|---|
| Generic career frameworks | Interview loops, resume principles, negotiation concepts | Yes |
| Domain knowledge | Industry structure, role expectations, common metrics | Usually yes, if non-confidential |
| User profile | Resume, goals, constraints, current role, target role | No |
| Session state | Current challenge, recent feedback, weekly notes | No |

This separation keeps the project reusable without leaking private information.

## 3. Build Repeatable Workflows

Useful workflows are narrow and structured:

- Weekly review: identify high-leverage work, bottlenecks, and next week's highest-value action.
- Mock interview: ask one question at a time, score the answer, then drill weak spots.
- Resume review: check positioning, proof, metrics, and role fit.
- Strategy review: assess clarity, strategic logic, audience fit, and missing evidence.
- Offer evaluation: compare learning, scope, compensation, risk, brand, and lifestyle fit.

Each workflow should define:

- Required inputs
- Diagnostic questions
- Evaluation rubric
- Output format
- Next action

## 4. Prompt Design

The system prompt should do four things:

1. Define the coach's scope.
2. Load the user's local context.
3. Load the selected workflow.
4. Enforce coaching behavior.

Recommended behavior rules:

- Ask up to two clarifying questions when context is missing.
- Do not give generic motivational advice.
- Tie recommendations to the user's target role and constraints.
- Name the tradeoff behind each recommendation.
- End with one action that can be completed within seven days.

## 5. Implementation Options

### Local Prompt/Skill

Best for users who work in agent tools. Store context and templates as Markdown and let the agent load them.

### Local Web App

Best for repeat use. A minimal app can:

- Load local Markdown context files
- Offer buttons for each workflow
- Send assembled prompts to a model provider
- Save local conversation history

### Hosted App

Use this only after privacy boundaries are clear. A hosted version needs authentication, encryption, retention controls, and a way for users to delete data.

## 6. Evaluation

Test the coach with real but sanitized scenarios:

- Did it ask diagnostic questions before advising?
- Did it avoid generic advice?
- Did it cite the relevant context?
- Was the next action concrete?
- Did it preserve privacy boundaries?

The best signal is whether the user takes the suggested action and returns with better context next time.

