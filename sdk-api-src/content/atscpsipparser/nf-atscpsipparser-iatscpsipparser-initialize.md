---
UID: NF:atscpsipparser.IAtscPsipParser.Initialize
title: IAtscPsipParser::Initialize (atscpsipparser.h)
description: This topic applies to Update Rollup 2 for Microsoft Windows XP Media Center Edition 2005 and later.
helpviewer_keywords: ["IAtscPsipParser interface [Microsoft TV Technologies]","Initialize method","IAtscPsipParser.Initialize","IAtscPsipParser::Initialize","IAtscPsipParserInitialize","Initialize","Initialize method [Microsoft TV Technologies]","Initialize method [Microsoft TV Technologies]","IAtscPsipParser interface","atscpsipparser/IAtscPsipParser::Initialize","mstv.iatscpsipparser_initialize"]
old-location: mstv\iatscpsipparser_initialize.htm
tech.root: mstv
ms.assetid: 7a4d4d17-4fc5-481c-bcf8-0f68b2f0a8e2
ms.date: 12/05/2018
ms.keywords: IAtscPsipParser interface [Microsoft TV Technologies],Initialize method, IAtscPsipParser.Initialize, IAtscPsipParser::Initialize, IAtscPsipParserInitialize, Initialize, Initialize method [Microsoft TV Technologies], Initialize method [Microsoft TV Technologies],IAtscPsipParser interface, atscpsipparser/IAtscPsipParser::Initialize, mstv.iatscpsipparser_initialize
req.header: atscpsipparser.h
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
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
f1_keywords:
 - IAtscPsipParser::Initialize
 - atscpsipparser/IAtscPsipParser::Initialize
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - atscpsipparser.h
api_name:
 - IAtscPsipParser.Initialize
---

# IAtscPsipParser::Initialize


## -description

This topic applies to Update Rollup 2 for Microsoft Windows XP Media Center Edition 2005 and later.
        



The <b>Initialize</b> method initializes this object.

## -parameters

### -param punkMpeg2Data [in]

Pointer to the <b>IUnknown</b> interface of the <a href="/previous-versions/windows/desktop/mstv/mpeg-2-sections-and-tables-filter">MPEG-2 Sections and Tables Filter</a> or another object that implements the <a href="/previous-versions/windows/desktop/api/mpeg2data/nn-mpeg2data-impeg2data">IMpeg2Data</a> interface.

## -returns

The method returns an <b>HRESULT</b>. Possible values include those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The <i>punkMpeg2Data</i> pointer does not expose the <b>IMpeg2Data</b> interface.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
NULL pointer argument.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
</table>

## -remarks

Until this method is called, all other methods on this interface fail.

## -see-also

<a href="/previous-versions/windows/desktop/api/atscpsipparser/nn-atscpsipparser-iatscpsipparser">IAtscPsipParser Interface</a>