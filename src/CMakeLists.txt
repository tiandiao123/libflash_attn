set(CMAKE_CUDA_FLAGS "${CMAKE_CUDA_FLAGS} --expt-relaxed-constexpr --expt-relaxed-constexpr --use_fast_math -t 8 \
                      -gencode=arch=compute_80,code=\\\"sm_80,compute_80\\\" \
                      ")

include_directories(${CUTLASS_DIR}/include)
include_directories(../include)

add_library(flash_attn SHARED
    flash_api.cpp
    flash_bwd_hdim128_bf16_sm80.cu
    flash_bwd_hdim128_fp16_sm80.cu
    flash_bwd_hdim160_bf16_sm80.cu
    flash_bwd_hdim160_fp16_sm80.cu
    flash_bwd_hdim192_bf16_sm80.cu
    flash_bwd_hdim192_fp16_sm80.cu
    flash_bwd_hdim224_bf16_sm80.cu
    flash_bwd_hdim224_fp16_sm80.cu
    flash_bwd_hdim256_bf16_sm80.cu
    flash_bwd_hdim256_fp16_sm80.cu
    flash_bwd_hdim32_bf16_sm80.cu
    flash_bwd_hdim32_fp16_sm80.cu
    flash_bwd_hdim64_bf16_sm80.cu
    flash_bwd_hdim64_fp16_sm80.cu
    flash_bwd_hdim96_bf16_sm80.cu
    flash_bwd_hdim96_fp16_sm80.cu
    flash_fwd_hdim128_bf16_sm80.cu
    flash_fwd_hdim128_fp16_sm80.cu
    flash_fwd_hdim160_bf16_sm80.cu
    flash_fwd_hdim160_fp16_sm80.cu
    flash_fwd_hdim192_bf16_sm80.cu
    flash_fwd_hdim192_fp16_sm80.cu
    flash_fwd_hdim224_bf16_sm80.cu
    flash_fwd_hdim224_fp16_sm80.cu
    flash_fwd_hdim256_bf16_sm80.cu
    flash_fwd_hdim256_fp16_sm80.cu
    flash_fwd_hdim32_bf16_sm80.cu
    flash_fwd_hdim32_fp16_sm80.cu
    flash_fwd_hdim64_bf16_sm80.cu
    flash_fwd_hdim64_fp16_sm80.cu
    flash_fwd_hdim96_bf16_sm80.cu
    flash_fwd_hdim96_fp16_sm80.cu
    flash_fwd_split_hdim128_bf16_sm80.cu
    flash_fwd_split_hdim128_fp16_sm80.cu
    flash_fwd_split_hdim160_bf16_sm80.cu
    flash_fwd_split_hdim160_fp16_sm80.cu
    flash_fwd_split_hdim192_bf16_sm80.cu
    flash_fwd_split_hdim192_fp16_sm80.cu
    flash_fwd_split_hdim224_bf16_sm80.cu
    flash_fwd_split_hdim224_fp16_sm80.cu
    flash_fwd_split_hdim256_bf16_sm80.cu
    flash_fwd_split_hdim256_fp16_sm80.cu
    flash_fwd_split_hdim32_bf16_sm80.cu
    flash_fwd_split_hdim32_fp16_sm80.cu
    flash_fwd_split_hdim64_bf16_sm80.cu
    flash_fwd_split_hdim64_fp16_sm80.cu
    flash_fwd_split_hdim96_bf16_sm80.cu
    flash_fwd_split_hdim96_fp16_sm80.cu
)

set_target_properties(flash_attn PROPERTIES CUDA_ARCHITECTURES "80")
