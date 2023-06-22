Jupiter/RADV 23.6 Release Notes / 2023-06-22
============================================

This new RADV release contains a bunch of new extension and features. Most
notable are GPL by default and many RT improvements. Though, RADV_PERFTEST=rt
is still needed on VanGogh because it can randomly hang.

New features
------------

- Implemented VK_EXT_pipeline_library_group_handles
- Implemented VK_EXT_image_sliced_view_of_3d on GFX10+
- Implemented VK_KHR_map_memory2
- Implemented VK_EXT_discard_rectangles version 2
- Implemented VK_EXT_attachment_feedback_loop_dynamic_state
- Implemented VK_EXT_dynamic_rendering_unused_attachments
- Implemented VK_KHR_fragment_shader_barycentric on GFX10.3+
- Implemented VK_EXT_depth_bias_control
- fullyCoveredFragmentShaderInputVariable on GFX9+
- primitiveUnderestimation on RADV/GFX9+
- extendedDynamicState3ColorBlendEquation
- extendedDynamicState3SampleLocationsEnable
- Enabled VK_EXT_graphics_pipeline_library by default
- Enabled VK_KHR_ray_tracing_pipeline by default on GFX10.3+ (except VanGogh)

Bug fixes
---------

TBD
