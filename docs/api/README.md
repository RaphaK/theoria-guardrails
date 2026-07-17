<!-- markdownlint-disable -->

# API Overview

## Modules

- [`theoriaguardrails.context`](./theoriaguardrails.context.md#module-theoriaguardrailscontext)
- [`theoriaguardrails.embeddings.basic`](./theoriaguardrails.embeddings.basic.md#module-theoriaguardrailsembeddingsbasic)
- [`theoriaguardrails.embeddings.index`](./theoriaguardrails.embeddings.index.md#module-theoriaguardrailsembeddingsindex)
- [`theoriaguardrails.rails.llm.config`](./theoriaguardrails.rails.llm.config.md#module-theoriaguardrailsrailsllmconfig): Module for the configuration of rails.
- [`theoriaguardrails.rails.llm.llmrails`](./theoriaguardrails.rails.llm.llmrails.md#module-theoriaguardrailsrailsllmllmrails): LLM Rails entry point.
- [`theoriaguardrails.streaming`](./theoriaguardrails.streaming.md#module-theoriaguardrailsstreaming)

## Classes

- [`basic.BasicEmbeddingsIndex`](./theoriaguardrails.embeddings.basic.md#class-basicembeddingsindex): Basic implementation of an embeddings index.
- [`basic.OpenAIEmbeddingModel`](./theoriaguardrails.embeddings.basic.md#class-openaiembeddingmodel): Embedding model using OpenAI API.
- [`basic.SentenceTransformerEmbeddingModel`](./theoriaguardrails.embeddings.basic.md#class-sentencetransformerembeddingmodel): Embedding model using sentence-transformers.
- [`index.EmbeddingModel`](./theoriaguardrails.embeddings.index.md#class-embeddingmodel): The embedding model is responsible for creating the embeddings.
- [`index.EmbeddingsIndex`](./theoriaguardrails.embeddings.index.md#class-embeddingsindex): The embeddings index is responsible for computing and searching a set of embeddings.
- [`index.IndexItem`](./theoriaguardrails.embeddings.index.md#class-indexitem): IndexItem(text: str, meta: Dict = <factory>)
- [`config.CoreConfig`](./theoriaguardrails.rails.llm.config.md#class-coreconfig): Settings for core internal mechanics.
- [`config.DialogRails`](./theoriaguardrails.rails.llm.config.md#class-dialograils): Configuration of topical rails.
- [`config.Document`](./theoriaguardrails.rails.llm.config.md#class-document): Configuration for documents that should be used for question answering.
- [`config.EmbeddingSearchProvider`](./theoriaguardrails.rails.llm.config.md#class-embeddingsearchprovider): Configuration of a embedding search provider.
- [`config.FactCheckingRailConfig`](./theoriaguardrails.rails.llm.config.md#class-factcheckingrailconfig): Configuration data for the fact-checking rail.
- [`config.InputRails`](./theoriaguardrails.rails.llm.config.md#class-inputrails): Configuration of input rails.
- [`config.Instruction`](./theoriaguardrails.rails.llm.config.md#class-instruction): Configuration for instructions in natural language that should be passed to the LLM.
- [`config.KnowledgeBaseConfig`](./theoriaguardrails.rails.llm.config.md#class-knowledgebaseconfig)
- [`config.MessageTemplate`](./theoriaguardrails.rails.llm.config.md#class-messagetemplate): Template for a message structure.
- [`config.Model`](./theoriaguardrails.rails.llm.config.md#class-model): Configuration of a model used by the rails engine.
- [`config.OutputRails`](./theoriaguardrails.rails.llm.config.md#class-outputrails): Configuration of output rails.
- [`config.Rails`](./theoriaguardrails.rails.llm.config.md#class-rails): Configuration of specific rails.
- [`config.RailsConfig`](./theoriaguardrails.rails.llm.config.md#class-railsconfig): Configuration object for the models and the rails.
- [`config.RailsConfigData`](./theoriaguardrails.rails.llm.config.md#class-railsconfigdata): Configuration data for specific rails that are supported out-of-the-box.
- [`config.RetrievalRails`](./theoriaguardrails.rails.llm.config.md#class-retrievalrails): Configuration of retrieval rails.
- [`config.SensitiveDataDetection`](./theoriaguardrails.rails.llm.config.md#class-sensitivedatadetection): Configuration of what sensitive data should be detected.
- [`config.SensitiveDataDetectionOptions`](./theoriaguardrails.rails.llm.config.md#class-sensitivedatadetectionoptions)
- [`config.SingleCallConfig`](./theoriaguardrails.rails.llm.config.md#class-singlecallconfig): Configuration for the single LLM call option for topical rails.
- [`config.TaskPrompt`](./theoriaguardrails.rails.llm.config.md#class-taskprompt): Configuration for prompts that will be used for a specific task.
- [`config.UserMessagesConfig`](./theoriaguardrails.rails.llm.config.md#class-usermessagesconfig): Configuration for how the user messages are interpreted.
- [`llmrails.LLMRails`](./theoriaguardrails.rails.llm.llmrails.md#class-llmrails): Rails based on a given configuration.
- [`streaming.StreamingHandler`](./theoriaguardrails.streaming.md#class-streaminghandler): Streaming async handler.

## Functions

- [`basic.init_embedding_model`](./theoriaguardrails.embeddings.basic.md#function-init_embedding_model): Initialize the embedding model.
