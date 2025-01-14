---
UID: NF:prcomoem.IPrintOemUIMXDC.AdjustImageCompression
title: IPrintOemUIMXDC::AdjustImageCompression (prcomoem.h)
description: The IPrintOemUIMXDC::AdjustImageCompression method allows an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of compression level for JPEG or PNG images.
old-location: print\iprintoemuimxdc_adjustimagecompression.htm
tech.root: print
ms.assetid: d9606c9b-4a47-4e83-ad8a-ef82e2c70de3
ms.date: 04/20/2018
ms.keywords: AdjustImageCompression, AdjustImageCompression method [Print Devices], AdjustImageCompression method [Print Devices],IPrintOemUIMXDC interface, IPrintOemUIMXDC interface [Print Devices],AdjustImageCompression method, IPrintOemUIMXDC.AdjustImageCompression, IPrintOemUIMXDC::AdjustImageCompression, prcomoem/IPrintOemUIMXDC::AdjustImageCompression, print.iprintoemuimxdc_adjustimagecompression, print_unidrv-pscript_ui_a4a6182b-9471-473a-9c16-15f56dcddda5.xml
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: Available with Windows Vista and later versions of Unidrvui.dll and Ps5ui.dll, which are redistributable. This method is also available for XPSDrv drivers in Microsoft Windows XP if you have installed the XPS Essentials Pack.
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
- IPrintOemUIMXDC.AdjustImageCompression
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUIMXDC::AdjustImageCompression


## -description


The <code>IPrintOemUIMXDC::AdjustImageCompression</code> method allows an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of compression level for JPEG or PNG images.


## -parameters




### -param hPrinter

A handle to the printer that is currently being queried.


### -param cbDevMode

The size of the <a href="https://docs.microsoft.com/windows/desktop/api/wingdi/ns-wingdi-_devicemodew">DEVMODE</a> structure, including appended data.


### -param pDevMode

A pointer to the DEVMODE structure that contains the current device settings.


### -param cbOEMDM

The number of bytes in the vendor-provided section of the DEVMODE structure.


### -param pOEMDM

A pointer to the data that is contained in the vendor portion of the DEVMODE structure that <i>pDevMode</i> points to.


### -param pCompressionMode

A pointer to the current compression level. <i>pCompressionMode</i> is an enum type specified in Mxdc.h.


## -returns



<code>AdjustImageCompression</code> returns S_OK if the method succeeds. Otherwise, this method should return E_NOTIMPL if the plug-in does not support the method, or any appropriate failure value if the plug-in cannot complete the operation. For more information, see the following Remarks section.




## -remarks



The <code>IPrintOemUIMXDC::AdjustImageCompression</code> method affects JPEG and PNG images that are generated by Microsoft XPS Document Converter (MXDC). The <code>IPrintOemUIMXDC::AdjustImageCompression</code> method does not affect the JPEG and PNG images that are sent directly by applications to GDI via the GDI JPEG/PNG image pass-through mechanism (<a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-tagdevinfo">BMF_JPEG</a>, <b>BMF_PNG</b>).

The core drivers, UnidrvUI.dll and PS5UI.dll, do not modify the image compression settings. The plug-in, however, can change the value that is initially provided to the MXDC by the GDI print path.

The <i>pCompressionMode</i> parameter has one of the following predefined values.

<table>
<tr>
<th>ENUM Type  </th>
<th>Value                    </th>
<th>Meaning</th>
</tr>
<tr>
<td>
MXDC_IMAGETYPE_JPEGHIGH_COMPRESSION

</td>
<td>
1                            

</td>
<td>
Lowest quality and smallest file size

</td>
</tr>
<tr>
<td>
MXDC_IMAGETYPE_JPEGMEDIUM_COMPRESSION

</td>
<td>
2                            

</td>
<td>
Medium quality and medium file size

</td>
</tr>
<tr>
<td>
MXDC_IMAGETYPE_JPEGLOW_COMPRESSION

</td>
<td>
3

</td>
<td>
High quality and large file size

</td>
</tr>
<tr>
<td>
MXDC_IMAGETYPE_PNG

</td>
<td>
4

</td>
<td>
Highest quality and largest file size

</td>
</tr>
</table>
 

The <i>pCompressionMode</i> parameter is IN OUT. All other parameters for this function are input only.

If the plug-in cannot complete the operation, it should return an appropriate failure HRESULT, which causes the current print job to fail.



