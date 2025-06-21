A version of Unity Webrtc's M116 release that works on Meta Quest headsets with Vulkan. The Android plugin has been simply rebuilt for Android with EXPORT_HANDLE = false in VulkanTexture2D::Init function of VulkanTexture2D.cpp . Tested on Meta Quest 3.

Only the Android plugin(Runtime/Plugins/Android) has been rebuilt since this workaround is targetted towards Meta Quest.
