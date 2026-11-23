# Requirements and diagrams

Use this guide when shaping an MVP or reviewing a flow with unclear actors, authority, or failure behavior. It adapts the scenario and requirements method from the Software Engineering requirements lab.

1. Read the project’s existing decisions. Identify the first user, the outcome they need, and the conditions the project already accepts. Label assumptions and questions as open until they are resolved.
2. Write a normal scenario and the failure scenarios that change the outcome. Name the actor, trigger, observable result, and who can establish that result.
3. Sketch the smallest diagram that settles the open question. Review it during grilling and use the project's glossary for names.
4. Trace each promised behavior from **scenario → acceptance criterion → test or observation**. Put that chain in the owning spec or issue, then choose the smallest slice that demonstrates a complete outcome.

| Diagram | Use it to settle |
| --- | --- |
| System context or use case | Who acts, what they can do, and which system owns each boundary |
| Activity or sequence | The order of actions and the response to an interruption, rejection, or retry |
| State | What each status means, what can change it, and what evidence establishes completion |

For a payment sandbox, consider a lost response after a simulated QR payment posts. The acceptance criterion should say what the customer sees when retrying and that the journal records a single transfer. The test should exercise the retry after the first attempt has already posted.

For a whole MVP, keep an architecture index in the owning project and link it from the specification. Use an actor and use-case map for scope, a system context diagram for trust and authority, and add lifecycle and logical data diagrams where state changes or data relationships enforce core behavior. Link detailed scenarios from the index. Review each diagram against the accepted decisions before landing it, and record open design choices in the index.

Keep diagrams with the project decision or spec they explain. Link the source file when later sessions will need to update it. See `.local/README.md` for the course references when available.
