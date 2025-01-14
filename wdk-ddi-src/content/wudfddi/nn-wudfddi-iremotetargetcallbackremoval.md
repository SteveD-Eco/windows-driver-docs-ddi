---
UID: NN:wudfddi.IRemoteTargetCallbackRemoval
title: IRemoteTargetCallbackRemoval (wudfddi.h)
description: The IRemoteTargetCallbackRemoval interface provides callback functions that the framework calls to notify the driver about events that are associated with the removal of a remote I/O target.
old-location: wdf\iremotetargetcallbackremoval.htm
tech.root: wdf
ms.assetid: 72271173-8851-4980-9b52-f9e14f1fe071
ms.date: 02/26/2018
ms.keywords: IRemoteTargetCallbackRemoval, IRemoteTargetCallbackRemoval interface, IRemoteTargetCallbackRemoval interface,described, UMDFIoTargetObjectRef_7508512a-9bfc-4563-bf01-48e9caf6ba4f.xml, umdf.iremotetargetcallbackremoval, wdf.iremotetargetcallbackremoval, wudfddi/IRemoteTargetCallbackRemoval
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wudfddi.h
api_name:
- IRemoteTargetCallbackRemoval
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRemoteTargetCallbackRemoval interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IRemoteTargetCallbackRemoval</b> interface provides callback functions that the framework calls to notify the driver about events that are associated with the removal of a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRemoteTargetCallbackRemoval</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IRemoteTargetCallbackRemoval</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IRemoteTargetCallbackRemoval</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetqueryremove">IRemoteTargetCallbackRemoval::OnRemoteTargetQueryRemove</a>
</td>
<td align="left" width="63%">
A UMDF-based driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetqueryremove">OnRemoteTargetQueryRemove</a> event callback function determines whether a remote I/O target's device can be stopped and removed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecanceled">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveCanceled</a>
</td>
<td align="left" width="63%">
A UMDF-based driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecanceled">OnRemoteTargetRemoveCanceled</a> event callback function performs operations that are necessary when the operating system cancels the removal of a remote I/O target's device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecomplete">IRemoteTargetCallbackRemoval::OnRemoteTargetRemoveComplete</a>
</td>
<td align="left" width="63%">
A UMDF-based driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iremotetargetcallbackremoval-onremotetargetremovecomplete">OnRemoteTargetRemoveComplete</a> event callback function performs operations that are necessary after the operating system completes the removal of a remote I/O target's device.

</td>
</tr>
</table> 


## -remarks



If your driver supports an <b>IRemoteTargetCallbackRemoval</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a> must return the interface. 



