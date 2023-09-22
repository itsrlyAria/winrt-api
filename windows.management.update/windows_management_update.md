---
-api-id: N:Windows.Management.Update
-api-type: winrt namespace
---

<!-- Namespace syntax.
namespace Windows.Management.Update 
-->

# Windows.Management.Update

## -description
This API allows Management tools or IT Administrators directly (with administrative privilages on a device) to register and control various aspects of updating. This includes triggering a restart using the Windows Update restart flow with commercial attribution.   

## -remarks
This API is only available in Windows 11, version 22H2 and above. Further, the Preview Builds portion is designed for IoT OEMs only and it's expected that the OEM of the device will create a settings page within the [Windows Device Portal](/windows/iot-core/manage-your-device/deviceportal) for device configuration properties. All of the other portions are for all device types including client, server, IoT, etc. 

## -see-also


## -examples
This example demonstrates how a user can determine if their device is receiving preview builds or if there are problems preventing the device from getting preview builds.

```csharp
public string GetErrorMessage() 
{ 
    PreviewBuildsManager manager = PreviewBuildsManager.GetDefault(); 
    if (manager != null) 
    { 
        PreviewBuildsState state = manager.GetCurrentState(); 
        if (state.Properties.ContainsKey("ErrorMessage")) 
        { 
            return state.Properties["ErrorMessage"].ToString(); 
        } 
    } 
    return String.Empty; 
} 
```
