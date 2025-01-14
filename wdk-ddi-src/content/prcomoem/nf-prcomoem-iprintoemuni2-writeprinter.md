---
UID: NF:prcomoem.IPrintOemUni2.WritePrinter
title: IPrintOemUni2::WritePrinter (prcomoem.h)
description: The IPrintOemUni2::WritePrinter method, if supported, enables a rendering plug-in to capture all output data generated by a Unidrv driver.
old-location: print\iprintoemuni2_writeprinter.htm
tech.root: print
ms.assetid: 61901d4d-7821-40b4-aaef-fd679985abb3
ms.date: 04/20/2018
ms.keywords: IPrintOemUni2 interface [Print Devices],WritePrinter method, IPrintOemUni2.WritePrinter, IPrintOemUni2::WritePrinter, WritePrinter, WritePrinter method [Print Devices], WritePrinter method [Print Devices],IPrintOemUni2 interface, prcomoem/IPrintOemUni2::WritePrinter, print.iprintoemuni2_writeprinter, print_unidrv-pscript_rendering_8dfd9075-d0a9-451b-bb31-9e1a55c16c1c.xml
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
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
- prcomoem.h
api_name:
- IPrintOemUni2.WritePrinter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUni2::WritePrinter


## -description


The <code>IPrintOemUni2::WritePrinter</code> method, if supported, enables a rendering plug-in to capture all output data generated by a Unidrv driver. If this method is not supported, the output data would otherwise be sent to the spooler in a call to the spooler's WritePrinter API (described in the Microsoft Windows SDK documentation).


## -parameters




### -param pdevobj

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_devobj">DEVOBJ</a> structure.


### -param pBuf

Pointer to the first byte of an array of bytes that contains the output data generated by the Unidrv driver.


### -param cbBuffer

Specifies the size, in bytes, of the array pointed to by <i>pBuf</i>.


### -param pcbWritten

Pointer to a DWORD value that receives the number of bytes of data that were successfully sent to the plug-in.


## -returns



If successful, this method returns S_OK. Otherwise, this method should return an appropriate value in the returned HRESULT.




## -remarks



At <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-drvenablepdev">DrvEnablePDEV</a> time, the Unidrv driver calls this method with <i>pBuf</i> and <i>pdevobj</i> set to <b>NULL</b>, and <i>cbBuf</i> set to 0, to detect whether the plug-in implements this function. The plug-in should return S_OK to indicate it implements this method, and should return E_NOTIMPL otherwise.

This method should report the number of bytes written to the spooler's <b>WritePrinter</b> function in <i>pcbWritten</i>. A value of zero carries no special meaning; errors must be reported through the returned HRESULT.

The <code>IPrintOemUni2::WritePrinter</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemuni-getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "WritePrinter" as input.



