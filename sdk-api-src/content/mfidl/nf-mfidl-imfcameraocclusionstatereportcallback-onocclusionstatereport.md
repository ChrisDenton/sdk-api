---
UID: NF:mfidl.IMFCameraOcclusionStateReportCallback.OnOcclusionStateReport
tech.root: mf
title: IMFCameraOcclusionStateReportCallback::OnOcclusionStateReport
ms.date: 05/25/2021
targetos: Windows
description: Called by the system when the camera occlusion state changes.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: mfidl.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - mfidl.h
api_name:
 - IMFCameraOcclusionStateReportCallback::OnOcclusionStateReport
f1_keywords:
 - IMFCameraOcclusionStateReportCallback::OnOcclusionStateReport
 - mfidl/IMFCameraOcclusionStateReportCallback::OnOcclusionStateReport
dev_langs:
 - c++
---

## -description

Called by the system when the camera occlusion state changes.

## -parameters

### -param occlusionStateReport

An [IMFCameraOcclusionStateReport](nn-mfidl-imfcameraocclusionstatereport.md) that can be used to obtain the new camera occlusion state.

## -returns

If this method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

Register the callback interface by calling [MFCreateCameraOcclusionStateMonitor](nf-mfidl-mfcreatecameraocclusionstatemonitor.md).

## -see-also

[MFCreateCameraOcclusionStateMonitor](nf-mfidl-mfcreatecameraocclusionstatemonitor.md)

[IMFCameraOcclusionStateReport](nn-mfidl-imfcameraocclusionstatereport.md)

