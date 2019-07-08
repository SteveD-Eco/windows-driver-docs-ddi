---
UID: NS:d3dukmdt._D3DGPU_PHYSICAL_ADDRESS
title: _D3DGPU_PHYSICAL_ADDRESS (d3dukmdt.h)
description: The GPU's physical address.
ms.assetid: c0e476ef-bd49-46e6-8e16-eabb6178f9d7
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _D3DGPU_PHYSICAL_ADDRESS, D3DGPU_PHYSICAL_ADDRESS, 
req.header: d3dukmdt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DGPU_PHYSICAL_ADDRESS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3dukmdt.h
api_name: 
- _D3DGPU_PHYSICAL_ADDRESS
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# _D3DGPU_PHYSICAL_ADDRESS structure

## -description

The GPU's physical address. In the DDI, physical memory references always take the form of a SegmentId::SegmentOffset pair.
The D3DGPU_PHYSICAL_ADDRESS structure is used in several DDIs.


## -struct-fields

### -field SegmentId

The driver ID of a memory segment. Note that the driver segment IDs start from 1. When SegmentId is 0, the allocation is in system memory and SegmentOffset is equal to the system memory physical address.

### -field SegmentOffset
 
The segment offset. The offset in bytes from the start of a memory segment when SegmentId is greater than 0. This is physical memory address when SegmentId is 0.

## -remarks

## -see-also
