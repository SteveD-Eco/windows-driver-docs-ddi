---
UID: NF:fwpsk.FwpsReferencevSwitchPacketContext0
title: FwpsReferencevSwitchPacketContext0 function (fwpsk.h)
description: This function is not supported.
old-location: netvista\fwpsreferencevswitchpacketcontext0.htm
tech.root: netvista
ms.assetid: F4F5005F-2BDA-4E58-A06A-2A4F1D34776D
ms.date: 05/02/2018
ms.keywords: FwpsReferencevSwitchPacketContext0, FwpsReferencevSwitchPacketContext0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsReferencevSwitchPacketContext0, netvista.fwpsreferencevswitchpacketcontext0
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsReferencevSwitchPacketContext0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsReferencevSwitchPacketContext0 function


## -description


This function is not supported.


## -parameters




### -param packetContext

The <b>vSwitchPacketContext</b> value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to callouts during virtual switch transport layer classifies (the <b>FWPS_L2_METADATA_FIELD_VSWITCH_SOURCE_PORT_ID</b> bit will be set in the  <b>currentL2MetadataValues</b> member). 


## -returns



None.




## -remarks




    The  <b>FwpsReferencevSwitchPacketContext0</b> function processes the <b>vSwitchPacketContext</b> member  in  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure.


  
  




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsdereferencevswitchpacketcontext0">FwpsDereferencevSwitchPacketContext0</a>
 

 

