A version of Unity Webrtc's M116 release that works on Meta Quest headsets with Vulkan. The Android plugin has been simply rebuilt for Android with EXPORT_HANDLE = false in VulkanTexture2D::Init function of VulkanTexture2D.cpp . Tested on Meta Quest 3.

Only the Android plugin(Runtime/Plugins/Android) has been rebuilt since this workaround is targetted towards Meta Quest.

Why this build? <br/>
1. 3.0.0-pre8 doesn't initialize on Meta Quest with Vulkan. Original comment: https://github.com/Unity-Technologies/com.unity.webrtc/issues/1085#issuecomment-2992260866
2. For VR it is generally recommended to use MSAA. As of this commit, there is no way to use a custom Scriptable Render Feature with MSAA+Singlepass and OpenGL ES3(https://issuetracker.unity3d.com/issues/quest-gles3-transparent-materials-disappear-due-to-fullscreenrenderpass-on-quest-when-multiview-slash-spi-is-used-with-msaa-on-opengles3). Vulkan is the only way to avail the beniits of SPI/Multiview with MSAA enabled if you use custom render passes. (Unless you are writing your own pipeline, then I don't know if the bug still happens.

