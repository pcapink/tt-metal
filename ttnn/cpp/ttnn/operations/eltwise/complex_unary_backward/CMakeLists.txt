add_library(ttnn_op_eltwise_complex_unary_backward ${LIB_TYPE})
add_library(TTNN::Ops::Eltwise::Complex::Unary::Backward ALIAS ttnn_op_eltwise_complex_unary_backward)

target_precompile_headers(ttnn_op_eltwise_complex_unary_backward REUSE_FROM TT::CommonPCH)
TT_ENABLE_UNITY_BUILD(ttnn_op_eltwise_complex_unary_backward)

target_sources(ttnn_op_eltwise_complex_unary_backward PRIVATE device/complex_unary_backward_op.cpp)

target_include_directories(ttnn_op_eltwise_complex_unary_backward PRIVATE ${FixmeOpIncDirs})
target_link_libraries(
    ttnn_op_eltwise_complex_unary_backward
    PRIVATE
        TT::Metalium
        TTNN::Core
)

install(TARGETS ttnn_op_eltwise_complex_unary_backward LIBRARY COMPONENT tar)
