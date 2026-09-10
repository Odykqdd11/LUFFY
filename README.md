# LUFFY Development Repository

> 🚧 **Development Branch** - This is the main development repository for LUFFY (Learning to Reason Under Off‑Policy Guidance)

## About LUFFY

LUFFY is a reinforcement learning framework that bridges the gap between zero-RL and imitation learning by incorporating off-policy reasoning traces into the training process. This repository contains the core implementation and development work.

## 🔧 Development Status

This repository is under active development. Many features are currently being implemented or need refactoring.

## 🚀 Quick Start

⚠️ **Note**: This development version has incomplete implementations. Many features are marked as TODO and need to be completed before production use.

```bash
# Clone the repository
git clone <repository-url>
cd LUFFY

# Install dependencies
pip install -r luffy/requirements.txt

# Note: Some functionality is incomplete - check TODO list below for details
```

## 📁 Repository Structure

```
LUFFY/
├── luffy/          # Core LUFFY implementation
├── eval_scripts/   # Evaluation scripts
├── exp_scripts/   # Experiment scripts
├── data/          # Data processing
└── figures/      # Visualization assets
```

## ⚠️ Development Notes

- This is a **development version** with incomplete implementations
- Many functions contain TODO markers indicating pending work
- OpenAI API integration is implemented, while Gemini/Vertex AI integration remains a placeholder
- FSDP and distributed training features need completion


### 🔴 High Priority TODOs

- **API Integration**: Gemini/Vertex AI API implementation still needs completion
- **Reward System**: Parallel processing and validation for reward computation  
- **FSDP Training**: Model loading and distributed training setup
- **Data Processing**: Batch dimension operations are implemented; remaining optimization TODOs remain

### 📝 Complete TODO List

- [x] **luffy/deepscaler/utils.py:45** - Implement OpenAI API client initialization
- [x] **luffy/deepscaler/utils.py:46** - Add proper authentication handling
- [x] **luffy/deepscaler/utils.py:47** - Implement exponential backoff retry logic for rate limits
- [x] **luffy/deepscaler/utils.py:48** - Add comprehensive error handling for different API errors
- [x] **luffy/deepscaler/utils.py:49** - Implement response parsing and validation
- [ ] **luffy/deepscaler/utils.py:50** - Add logging for API calls and errors
- [ ] **luffy/deepscaler/utils.py:51** - Support batch processing for multiple prompts
- [ ] **luffy/deepscaler/utils.py:52** - Add timeout configuration for API calls
- [ ] **luffy/deepscaler/utils.py:53** - Implement Vertex AI initialization and authentication
- [ ] **luffy/deepscaler/utils.py:54** - Configure safety settings for content generation
- [ ] **luffy/deepscaler/utils.py:55** - Set up GenerativeModel with proper system instructions
- [ ] **luffy/deepscaler/utils.py:56** - Implement retry logic with exponential backoff
- [ ] **luffy/deepscaler/utils.py:57** - Add comprehensive error handling for API access issues
- [ ] **luffy/deepscaler/utils.py:58** - Handle rate limiting and quota management
- [ ] **luffy/deepscaler/utils.py:59** - Implement response validation and text extraction
- [ ] **luffy/deepscaler/utils.py:60** - Add support for different generation configurations
- [ ] **luffy/deepscaler/system_prompts.py:1** - Review and clean up system prompts
- [ ] **luffy/deepscaler/globals.py:1** - Verify global configuration values
- [ ] **luffy/deepscaler/rewards/math_reward.py:1** - Validate math reward implementation
- [ ] **luffy/deepscaler/rewards/reward_types.py:1** - Confirm reward type definitions
- [ ] **luffy/deepscaler/rewards/math_utils/utils.py:1** - Audit math utility functions
- [ ] **luffy/scripts/data/deepscaler_dataset.py:1** - Check dataset loading logic
- [ ] **luffy/scripts/data/prepare_filter_dataset.py:1** - Verify filtering pipeline
- [ ] **luffy/scripts/data/prepare_openr1_data.py:1** - Validate OpenR1 data preparation
- [ ] **luffy/scripts/data/prepare_openr1_data_spec_sys.py:1** - Check specialized system prompt data prep
- [ ] **luffy/scripts/data/prepare_openr1_data_v6.py:1** - Review v6 data preparation changes
- [ ] **eval_scripts/collect_results.py:1** - Ensure result collection handles all formats
- [ ] **eval_scripts/generate_vllm.py:1** - Validate vLLM generation workflow
- [ ] **eval_scripts/oat_math_grader.py:1** - Audit math grading accuracy
- [ ] **luffy/test.py:1** - Clean up and organize test cases
- [ ] **luffy/verl/verl/mix_src/main_mix_ppo.py:1** - Review mixed PPO training flow
- [ ] **luffy/verl/verl/mix_src/main_ppo_new_reward.py:1** - Check new reward PPO flow
- [ ] **luffy/verl/verl/mix_src/math_verify_reward.py:1** - Validate math verification reward
- [ ] **luffy/verl/verl/mix_src/mix_actor.py:1** - Audit mixed actor implementation
- [ ] **luffy/verl/verl/mix_src/mix_core_alg.py:1** - Review core algorithm changes
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:1** - Check FSDP worker integration
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:1** - Validate mixed trainer flow
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:1** - Check accumulator rebatching
- [ ] **luffy/verl/verl/mix_src/mix_vllm_rollout.py:1** - Review mixed vLLM rollout
- [ ] **luffy/verl/verl/mix_src/reward_with_format.py:1** - Check format-aware reward
- [ ] **luffy/verl/verl/mix_src/rl_dataset_with_target.py:1** - Validate target-aware RL dataset
- [ ] **luffy/verl/verl/mix_src/test.py:1** - Clean mix-source test file
- [ ] **luffy/verl/verl/mix_src/config/ppo_trainer.yaml:1** - Audit mixed PPO config
- [ ] **luffy/verl/verl/models/__init__.py:1** - Confirm model exports
- [ ] **luffy/verl/verl/models/registry.py:21** - (sgm): HF may supported more than listed here, we should add more after testing
- [ ] **luffy/verl/verl/models/transformers/llama.py:88** - These transpose are quite inefficient but Flash Attention requires the layout [batch_size, sequence_length, num_heads, head_dim]. We would need to refactor the KV cache
- [ ] **luffy/verl/verl/protocol.py:114** - Implement batch dimension folding for efficient processing
- [ ] **luffy/verl/verl/protocol.py:115** - Add validation for batch size compatibility
- [ ] **luffy/verl/verl/protocol.py:116** - Handle edge cases where batch_size is not divisible by new_batch_size
- [ ] **luffy/verl/verl/protocol.py:117** - Optimize memory usage during tensor reshaping
- [ ] **luffy/verl/verl/protocol.py:118** - Add support for different tensor types and shapes
- [ ] **luffy/verl/verl/protocol.py:131** - Implement batch dimension unfolding functionality
- [ ] **luffy/verl/verl/protocol.py:132** - Add support for variable batch dimensions
- [ ] **luffy/verl/verl/protocol.py:133** - Optimize tensor view operations for performance
- [ ] **luffy/verl/verl/protocol.py:134** - Handle non-tensor batch data reshaping properly
- [ ] **luffy/verl/verl/protocol.py:135** - Add error handling for invalid batch dimensions
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:77** - add checkpoint manager
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:140** - (zhangchi.usc1992):
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:159** - Implement model loading with proper initialization context
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:160** - Add support for different model types and configurations
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:161** - Implement memory-efficient model loading for large models
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:162** - Add model validation and compatibility checks
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:165** - Complete model loading implementation
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:166** - Add support for custom model architectures
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:167** - Implement proper dtype and attention configuration
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:170** - Implement gradient checkpointing configuration
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:171** - Add memory usage optimization strategies
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:172** - Configure mixed precision training settings
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:173** - Implement FSDP sharding and wrapping policies
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:174** - Add CPU offloading configuration for memory optimization
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:175** - Set up distributed training parameters properly
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:178** - Initialize FSDP wrapped model
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:301** - add a unified tracking
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:318** - (zhangchi.usc1992) add back checkpoint manager. Currently, it blocks when uploading to hdfs. So very slow.
- [ ] **luffy/verl/verl/trainer/main_ppo.py:50** - Implement reward computation for different data sources
- [ ] **luffy/verl/verl/trainer/main_ppo.py:53** - Add support for parallel processing of reward computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:56** - Implement proper sequence decoding and validation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:59** - Add thread-safe logging and debugging functionality
- [ ] **luffy/verl/verl/trainer/main_ppo.py:62** - Optimize memory usage for large batch processing
- [ ] **luffy/verl/verl/trainer/main_ppo.py:64** - Apply appropriate reward function based on data source
- [ ] **luffy/verl/verl/trainer/main_ppo.py:67** - Handle edge cases and error conditions
- [ ] **luffy/verl/verl/trainer/main_ppo.py:70** - Implement batch-wise reward computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:73** - Add proper error handling and validation
- [ ] **luffy/verl/verl/trainer/main_eval.py:1** - Validate evaluation entrypoint
- [ ] **luffy/verl/verl/trainer/main_generation.py:1** - Audit generation entrypoint
- [ ] **luffy/verl/verl/trainer/config/ppo_trainer.yaml:1** - Review PPO trainer config defaults
- [ ] **luffy/verl/verl/utils/config.py:1** - Confirm utility config loading
- [ ] **luffy/verl/verl/utils/distributed.py:1** - Check distributed helper functions
- [ ] **luffy/verl/verl/utils/flops_counter.py:1** - Audit FLOP counting logic
- [ ] **luffy/verl/verl/utils/fs.py:1** - Validate filesystem helper functions
- [ ] **luffy/verl/verl/utils/fsdp_utils.py:1** - Review FSDP utility functions
- [ ] **luffy/verl/verl/utils/hdfs_io.py:1** - Check HDFS I/O helpers
- [ ] **luffy/verl/verl/utils/import_utils.py:1** - Confirm import helper behavior
- [ ] **luffy/verl/verl/utils/logging_utils.py:1** - Validate logging helper functions
- [ ] **luffy/verl/verl/utils/megatron_utils.py:1** - Review Megatron utility functions
- [ ] **luffy/verl/verl/utils/memory_buffer.py:1** - Audit memory buffer implementation
- [ ] **luffy/verl/verl/utils/model.py:1** - Validate model helper functions
- [ ] **luffy/verl/verl/utils/py_functional.py:1** - Review PyTorch functional helpers
- [ ] **luffy/verl/verl/utils/checkpoint/fsdp_checkpoint_manager.py:101** - shall we remove previous ckpt every save?
- [ ] **luffy/verl/verl/utils/checkpoint/fsdp_checkpoint_manager.py:135** - address optimizer is None
- [ ] **luffy/verl/verl/utils/dataset/sft_dataset.py:1** - Audit SFT dataset loading
- [ ] **luffy/verl/verl/utils/logger/logger.py:1** - Validate logger behavior
- [ ] **luffy/verl/verl/utils/megatron/parallel_state.py:1** - Review Megatron parallel state setup
- [ ] **luffy/verl/verl/workers/actor/actor.py:1** - Audit actor worker implementation
- [ ] **luffy/verl/verl/workers/critic/critic.py:1** - Validate critic worker implementation
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:88** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:117** - it seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:157** - (zhangchi.usc1992): 1. support create from random initialized model. 2. Support init from FSDP directly
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:225** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:233** - add transformer policy
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:252** - add more optimizer args into config
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:278** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:289** - a sharding manager that do nothing?
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:416** - here, we should return all metrics
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:811** - (sgm): we may need to extract it to dp_reward_model.py
- [ ] **luffy/verl/verl/workers/megatron_workers.py:720** - reward model use itself tokenizer instead of sft tokenizer
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:145** - (sgm): check why is bfloat16
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:192** - actually, we just need to control the sampling order.
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:233** - we may use the new schedule instead
- [ ] **luffy/verl/verl/workers/rollout/rollout.py:1** - Audit rollout worker implementation
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:49** - check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:56** - check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:82** - offload FSDP model weights
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:113** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:122** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:130** - shall we build a micro_dp group for vLLM when integrating with vLLM?
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:253** - (sgm): this may not be true for FSDP -> vLLM
- [ ] **luffy/verl/verl/third_party/vllm/worker.py:1** - Check vLLM worker integration
- [ ] **luffy/verl/verl/single_controller/base/base_worker.py:1** - Review base worker abstractions
- [ ] **luffy/verl/verl/single_controller/ray/ray_worker_group.py:1** - Validate Ray worker group behavior
- [ ] **luffy/verl/verl/models/llama/modeling_llama.py:1** - Audit Llama model implementation
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:588** - for better performance, the sp padding should be removed at each layer. Not sure the performance gap
- [ ] **luffy/verl/verl/models/transformers/config.py:1** - Review model config handling
- [ ] **luffy/verl/verl/models/transformers/weight_loader.py:1** - Validate weight loader behavior
- [ ] **luffy/verl/verl/models/weight_loader_registry.py:1** - Confirm weight loader registry behavior
- [ ] **luffy/verl/verl/protocol.py:1** - Audit protocol tensor handling
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:1** - Review Ray PPO trainer flow
- [ ] **luffy/verl/verl/trainer/ppo/ppo_trainer.py:1** - Audit PPO trainer core logic
- [ ] **luffy/verl/verl/utils/torch_functional.py:1** - Validate torch functional helpers
- [ ] **luffy/verl/verl/version/version.py:1** - Confirm version handling

## Next Steps

1. Complete the placeholder API integrations
2. Finish FSDP model loading and training setup
3. Implement reward computation improvements
4. Clean up TODO markers after verification
5. Update this README when TODOs are completed
