Loom traces made with the [MiniHF](https://github.com/JD-P/minihf) loom. The loom
is a inference front end for MiniHF, [TogetherAI](https://docs.together.ai/reference/inference),
[OpenAI Completions](https://platform.openai.com/docs/api-reference/completions),
and any other API compatible with them. It manages the users session as a branching
tree of diffs on the context, allowing the user to back up, try different versions
of a prompt, and generate multiple completions at the same time to find exactly
the right thing. In essence the loom makes weak models stronger by letting the
user rejection sample and branch, [giving you a preview of what better models
would be capable of](https://bmk.sh/2020/08/17/Building-AGI-Using-Language-Models/).
MiniLoom is inspired by [Janus's loom](https://generative.ink/posts/loom-interface-to-the-multiverse/),
but uses a better data structure to store the session. MiniLoom sessions can have
their branches extracted as training data for DPO/SPO/IPO/KTO without explicit
thumbs up or thumbs down feedback.

You may contribute your own sessions by submitting a pull request to this repository.
Keep in mind that by submitting you affirm that you hold all relevant copyrights
to and release your submitted text [into the public domain](https://creativecommons.org/publicdomain/zero/1.0/).

To install the loom do something like the following:

1. git clone [the MiniHF repository](https://github.com/JD-P/minihf)
2. cd loom
3. npm install
4. npm start

You can use Together AI's inference services to loom even if you do not own GPUs.
Because these sessions are intended to be used as training data submitting text
generated with Facebook's LLaMa series of models is a violation of their terms
of service, which prohibit using the LLaMa series to enhance other language models.
For this reason I suggest using models like
Mistral 7B ([HuggingFace](https://huggingface.co/mistralai/Mistral-7B-v0.1)) ([Together](https://api.together.xyz/playground/language/mistralai/Mistral-7B-v0.1)),
Mixtral ([HuggingFace](https://huggingface.co/mistralai/Mixtral-8x7B-v0.1/)) ([Together](https://api.together.xyz/playground/language/mistralai/Mixtral-8x7B-v0.1)),
and SOLAR-10 ([HuggingFace](https://huggingface.co/upstage/SOLAR-10.7B-v1.0)).

If you use the OpenAI Completions API with non-OpenAI models, be sure to change
your model name in the sidebar to reflect the model you are actually using, otherwise
the trace will record it as `code-davinci-002`.

Happy weaving!