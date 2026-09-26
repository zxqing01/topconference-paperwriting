# Conclusion, limitations, and statements

## Conclusion

Synthesize the problem addressed, the central design idea, and the strongest established outcome. Do not repeat the full abstract or list every module and experiment. Numerical results may be retained when they carry the conclusion; repeating every percentage is unnecessary.

A final interpretive sentence is useful when it identifies the supported research lesson. Delete generic lines such as “These results demonstrate the effectiveness of our approach” when they merely repeat the preceding measurements. Do not force a summary sentence after every result paragraph to prepare for the conclusion.

Match the verb to the evidence:

- **Preserves / maintains:** performance is retained within the stated scope; do not imply a statistical equivalence test unless one was conducted.
- **Improves:** the relevant comparison supports an increase; state its scope where ambiguity would otherwise arise.
- **Reduces:** identify the actual resource measured, such as FLOPs, latency, peak memory, or parameters.
- **Enables / guarantees:** use only when the claimed capability or formal guarantee has been established.

Changing one word from “preserving” to “improving” is a substantive claim change even if grammatically simple. Check the stated baseline and relevant metrics, then make only the requested edit if supported. Do not replace the entire conclusion to justify that word.

Avoid extending benchmark results into deployment readiness, safety guarantees, all-environment robustness, or a universal explanation without corresponding evidence.

## Limitations and future work

Follow actual venue requirements and the requested task. Distinguish a material boundary of the result from a speculative reviewer objection. Include meaningful assumptions, tested operating ranges, unavailable evidence relevant to a claim, and known failure modes where appropriate. Do not hide a real limitation, but do not turn an ordinary methods paragraph into a defensive inventory of everything the paper did not do.

Future work is optional unless required. Use a concrete next question motivated by the present result; avoid a generic list of larger models, more datasets, and real-world deployment. If the user requests only an appendix edit, do not append a new limitations discussion elsewhere.

## Reproducibility and other statements

Reproducibility prose should direct readers to the actual implementation details, data/protocol descriptions, assumptions, and available artifacts. It should not duplicate the entire training setup or promise code release without authorization.

Ethics, funding, author contributions, AI use, and anonymity are factual declarations. Do not infer their content from stylistic editing, invent an author's actions, or change them during an unrelated chapter revision. When the assignment is explicitly a submission or declaration audit, verify the target venue/year and flag factual questions for the author with a precise source. Do not present a convention as a mandatory statement.

For anonymous submissions, follow the current instructions for identifying material in the paper and supplement. A later camera-ready version may legitimately use different author information and acknowledgments. Keep the workflow stage explicit.

## Closing consistency check

Compare the conclusion with the introduction's contributions and the result tables. Confirm the same comparison baseline, metric scope, and efficiency boundary. Remove unsupported additions and needless repetition while retaining the paper's actual achievement.
