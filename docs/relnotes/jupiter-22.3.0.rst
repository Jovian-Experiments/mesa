Jupiter/Mesa 22.3.0 Release Notes / 2022-07-18
==============================================

This new RADV release contains mostly new extensions and bugfixes. The most
important feature is DGC (required by Halo Infinite). Few games are fixed like
Red Dead Redemption 2, Space Engineers, Hammerting, Star Citizen and probably
more. ACO added 16-bit improvements mostly for FSR. Also note that Zink/RADV is
really close to be conformant with GLES and GL46 on RDNA GPUs.

New features
------------

- Experimental implementation of VK_NV_device_generatd_commands for vd3d-proton
- Initial implementation of VK_KHR_performance_query on RDNA2
- Implemented VK_KHR_ray_tracing_maintenance1
- Implemented VK_EXT_border_color_swizzle on RDNA1+
- Implemented VK_EXT_image_2d_view_of_3d
- Implemented VK_EXT_non_seamless_cube_map
- Implemented VK_EXT_primitives_generated_query
- Implemented VK_EXT_shader_module_identifier
- Implemented VK_INTEL_shader_integer_functions2
- Various task/mesh shaders work
- Various raytracing and graphics pipeline library work
- Very preliminary bringup for GFX11

Performance fixes
-----------------

- Various raytracing improvements
- Various minor CPU improvements (mostly found with Zink)
- DCC retile improvements for read-only images
- Enabled a NIR pass to move discards on top (mostly for D3D9 games)
- Various 16-bit improvements in ACO

Bug fixes
---------

- Fixed the number of generated primitive queries between NGG GS and legacy
  path (very old bug)
- Fixed line stipple interaction with dynamic primitive topology
- Fixed one configuration bit for SQTT on RDNA2
- Fixed a hardware bug related to pipeline query states on RDNA2
  (https://gitlab.freedesktop.org/mesa/mesa/-/issues/6257)
- Fixed a memory leak of descriptor set layout
- Fixed rendering issues by disabling DCC for Senra Kagura Shinovi Versus
  (https://gitlab.freedesktop.org/mesa/mesa/-/issues/6469)
- Fixed conditional rendering on the compute queue
  (https://gitlab.freedesktop.org/mesa/mesa/-/issues/6533)
- Fixed disabling predication for subpass and image clears
- Fixed emitting markers for non-memory offset
- Fixed redundant subpass barriers due to erroneous comparison
- Fixed multiview for mesh shaders
- Fixed lowering GS intrinsics if NGG is disabled per pipeline
- Fixed GPU hangs with Hammerting by using radv_zero_vram
  (https://github.com/ValveSoftware/Proton/issues/4347#issuecomment-1141415515)
- Fixed CPU hangs with Halo Infinite due to missing BO references
- Fixed a bug related to NGG culling and user sample locations
- Fixed emitting SQTT packets on the transfer queue (for PRIME setups)
- Fixed GPU hangs with Space Engineers
  (https://gitlab.freedesktop.org/mesa/mesa/-/issues/5838)
- Fixed rendering issues by disabling DCC for Melty Blood Actress Again Current
  Code (https://github.com/ValveSoftware/Proton/issues/271)
- Fixed vkCmdCopyQueryResults -> vkCmdResetPool hazard
- Fixed memory explosion with Red Dead Redemption 2 by removing the
  radv_report_apu_as_dgpu workaround
- Fixed wide points/lines by configuring the guardband correctly
  (found with Zink)
- Fixed Star Citizen flickering lights
  (https://gitlab.freedesktop.org/mesa/mesa/-/issues/6564)
- Various other task/mesh/raytracing bugfixes
- Various Zink/RADV bugfixes (Zink/RADV is so close for GLCTS conformance)
- Various other ACO fixes (mostly RA failures)
- Various RADV_DEBUG=hang fixes to get more reliable reports
