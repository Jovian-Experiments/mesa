Jupiter/SteamOS 3.5 Release Notes / 2023-02-14
==============================================

This is a major RADV release because the last one was branched mid-july 2022.

New features
------------

- Implemented VK_AMD_shader_early_and_late_fragment_tests
- Implemented VK_EXT_attachment_feedback_loop_layout
- Implemented VK_EXT_descriptor_buffer
- Implemented VK_EXT_extended_dynamic_state3
- Implemented VK_EXT_graphics_pipeline_library (requires RADV_PERFTEST=gpl)
- Implemented VK_EXT_load_store_op_none
- Implemented VK_EXT_mesh_shader on RDNA2
- Implemented VK_EXT_mutable_descriptor_type
- Implemented VK_EXT_swapchain_colorspace
- Implemented VK_KHR_global_priority
- Implemented VK_KHR_present_id (requires vk_khr_present_wait=true)
- Implemented VK_KHR_present_wait (requires vk_khr_present_wait=true)
- Implemented VK_KHR_video_decode_h264 (requires RADV_PERFTEST=video_decode)
- Implemented VK_KHR_video_decode_h265 (requires RADV_PERFTEST=video_decode)
- Implemented VK_KHR_video_decode_queue (requires RADV_PERFTEST=video_decode)
- Implemented VK_KHR_video_queue (requires RADV_PERFTEST=video_decode)
- Added RDNA3 support
- Added extendedDynamicState2PatchControlPoints (VK_EXT_extended_dynamic_state2)
- Added support for R8G8B8, B8G8R8, R16G16B16 and 64-bit vertex buffer formats
- Added support for RMV (Radeon Memory Visualizer)
- Added support for RRA (Radeon Raytracing Analyzer)
- Various raytracing improvements (eg. Doom Eternal with RT working well)

Bug fixes
---------

- Fixed a stack overflow in NIR in the precompiling screen with Returnal
- Fixed black squares glitches in Resident Evil 4
- Fixed GPU hangs with NGG and GDS in various games (Resident Evil 4, Warhammer
  Chaosbane, Stree Fighter 6 ...)
- Fixed an ACO bug in Doom 2016 with Zink/RADV and RADV_PERFTEST=gpl
- Fixed primitives generated query with NGG culling
- Fixed NGG culling when conservative overrasterization is used
- Fixed RB+ with SRGB formats
- Fixed missing implementation of creating images from swapchain
  (ie. VK_KHR_swapchain)
- Fixed multiple resolves in the same subpass
- Fixed removing the PointSize built-in for polygon mode as points
- Fixed guardband with points or lines
- Fixed depth/stencil attachments with feedback loops
- Fixed dual-source blending with unused color outputs
- Fixed DCC corruption by invalidating L2 (only affects some RDNA2 chips)
- Fixed various compiler bugs (including NIR and ACO)
- Fixed various GPL bugs
- And probably...
