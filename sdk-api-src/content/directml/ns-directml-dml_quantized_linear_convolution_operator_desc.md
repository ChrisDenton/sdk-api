---
UID: NS:directml.DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC
title: DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC
description: Performs a convolution of the *FilterTensor* with the *InputTensor*. This operator performs forward convolution on quantized data. This operator is mathematically equivalent to dequantizing the inputs, convolving, and then quantizing the output.
helpviewer_keywords: ["DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC","DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC structure","direct3d12.dml_quantized_linear_convolution_operator_desc","directml/DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC"]
tech.root: directml
ms.date: 11/03/2020
req.header: directml.h
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
f1_keywords:
 - DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC
 - directml/DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - DirectML.h
api_name:
 - DML_QUANTIZED_LINEAR_CONVOLUTION_OPERATOR_DESC
---

## -description

Performs a convolution of the *FilterTensor* with the *InputTensor*. This operator performs forward convolution on quantized data. This operator is mathematically equivalent to dequantizing the inputs, convolving, and then quantizing the output. 

The quantize linear functions used by this operator are the linear quantization functions

### Dequantize function

```
f(Input, Scale, ZeroPoint) = (Input - ZeroPoint) * Scale
```

### Quantize function

```
f(Input, Scale, ZeroPoint) = clamp(round(Input / Scale) + ZeroPoint, Min, Max)
```

## -struct-fields

### -field InputTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor containing the input data. The expected dimensions of the *InputTensor* are `{ InputBatchCount, InputChannelCount, InputHeight, InputWidth }`. 

### -field InputScaleTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor containing the input scale data. The expected dimensions of the `InputScaleTensor` are `{ 1, 1, 1, 1 }`. This scale value is used for dequantizing the input values.

### -field InputZeroPointTensor

Type: _Maybenull\_ **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

An optional tensor containing the input zero point data. The expected dimensions of the *InputZeroPointTensor* are `{ 1, 1, 1, 1 }`. This zero point value is used for dequantizing the input values.

### -field FilterTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor containing the filter data. The expected dimensions of the *FilterTensor* are `{ FilterBatchCount, FilterChannelCount, FilterHeight, FilterWidth }`. 

### -field FilterScaleTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor containing the filter scale data. The expected dimensions of the `FilterScaleTensor` are `{ 1, 1, 1, 1 }` if per tensor quantization is required, or `{ 1, OutputChannelCount, 1, 1 }` if per channel quantization is required. This scale value is used for dequantizing the filter values.

### -field FilterZeroPointTensor

Type: _Maybenull\_ **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

An optional tensor containing the filter zero point data. The expected dimensions of the *FilterZeroPointTensor* are `{ 1, 1, 1, 1 }` if per tensor quantization is required, or `{ 1, OutputChannelCount, 1, 1 }` if per channel quantization is required. This zero point value is used for dequantizing the filter values.

### -field BiasTensor

Type: \_Maybenull\_ **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor containing the bias data. The bias tensor is a tensor containing data which is broadcasted across the output tensor at the end of the convolution which is added to the result. The expected dimensions of the BiasTensor are `{ 1, OutputChannelCount, 1, 1 }` for 4D. 

### -field OutputScaleTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor containing the output scale data. The expected dimensions of the OutputScaleTensor are `{ 1, 1, 1, 1 }`. This input scale value is used for quantizing the convolution output values.

### -field OutputZeroPointTensor

Type: _Maybenull\_ **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

An optional tensor containing the filter zero point data. The expected dimensions of the OutputZeroPointTensor are `{ 1, 1, 1, 1 }`. This input zero point value is used for quantizing the convolution the output values.

### -field OutputTensor

Type: **const [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc)\***

A tensor to write the results to. The expected dimensions of the OutputTensor are `{ OutputBatchCount, OutputChannelCount, OutputHeight, OutputWidth }`.

### -field DimensionCount

Type: [**UINT**](/windows/desktop/winprog/windows-data-types)

The number of spatial dimensions for the convolution operation. Spatial dimensions are the lower dimensions of the convolution filter tensor *FilterTensor*. This value also determines the size of the *Strides*, *Dilations*, *StartPadding*, and *EndPadding* arrays. Only a value of 2 is supported.

### -field Strides

Type: \_Field_size\_(DimensionCount) **const [UINT](/windows/desktop/WinProg/windows-data-types)\***

The strides of the convolution operation. These strides are applied to the convolution filter. They are separate from the tensor strides included in [DML_TENSOR_DESC](/windows/win32/api/directml/ns-directml-dml_tensor_desc).

### -field Dilations

Type: \_Field_size\_(DimensionCount) **const [UINT](/windows/desktop/WinProg/windows-data-types)\***

The Dilations of the convolution operation. Dilations are strides applied to the elements of the filter kernel. This has the effect of simulating a larger filter kernel by padding the internal filter kernel elements with zeros.

### -field StartPadding

Type: \_Field_size\_(DimensionCount) **const [UINT](/windows/desktop/WinProg/windows-data-types)\***

The padding values to be applied to the beginning of each spatial dimension of the filter and input tensor of the convolution operation. 

### -field EndPadding

Type: \_Field_size\_(DimensionCount) **const [UINT](/windows/desktop/WinProg/windows-data-types)\***

The padding values to be applied to the end of each spatial dimension of the filter and input tensor of the convolution operation.

### -field GroupCount

Type: [**UINT**](/windows/desktop/winprog/windows-data-types)

The number of groups which to divide the convolution operation into. *GroupCount* can be used to achieve depth-wise convolution by setting the *GroupCount* equal to the input channel count. This divides the convolution up into a separate convolution per input channel. 

## Availability
This operator was introduced in `DML_FEATURE_LEVEL_2_1`.

## Tensor constraints
* *FilterZeroPointTensor*, *InputScaleTensor*, *InputZeroPointTensor*, *OutputScaleTensor*, and *OutputZeroPointTensor* must have the same *DimensionCount*.
* *BiasTensor*, *FilterScaleTensor*, *FilterTensor*, *InputTensor*, and *OutputTensor* must have the same *DimensionCount*.
* *OutputTensor* and *OutputZeroPointTensor* must have the same *DataType*.
* *InputTensor* and *InputZeroPointTensor* must have the same *DataType*.
* *FilterTensor* and *FilterZeroPointTensor* must have the same *DataType*.

## Tensor support
### DML_FEATURE_LEVEL_4_0 and above
| Tensor | Kind | Supported dimension counts | Supported data types |
| ------ | ---- | -------------------------- | -------------------- |
| InputTensor | Input | 3 to 4 | INT8, UINT8 |
| InputScaleTensor | Input | 1 to 4 | FLOAT32 |
| InputZeroPointTensor | Optional input | 1 to 4 | INT8, UINT8 |
| FilterTensor | Input | 3 to 4 | INT8, UINT8 |
| FilterScaleTensor | Input | 3 to 4 | FLOAT32 |
| FilterZeroPointTensor | Optional input | 1 to 4 | INT8, UINT8 |
| BiasTensor | Optional input | 3 to 4 | INT32 |
| OutputScaleTensor | Input | 1 to 4 | FLOAT32 |
| OutputZeroPointTensor | Optional input | 1 to 4 | INT8, UINT8 |
| OutputTensor | Output | 3 to 4 | INT8, UINT8 |

### DML_FEATURE_LEVEL_2_1 and above
| Tensor | Kind | Supported dimension counts | Supported data types |
| ------ | ---- | -------------------------- | -------------------- |
| InputTensor | Input | 4 | INT8, UINT8 |
| InputScaleTensor | Input | 4 | FLOAT32 |
| InputZeroPointTensor | Optional input | 4 | INT8, UINT8 |
| FilterTensor | Input | 4 | INT8, UINT8 |
| FilterScaleTensor | Input | 4 | FLOAT32 |
| FilterZeroPointTensor | Optional input | 4 | INT8, UINT8 |
| BiasTensor | Optional input | 4 | INT32 |
| OutputScaleTensor | Input | 4 | FLOAT32 |
| OutputZeroPointTensor | Optional input | 4 | INT8, UINT8 |
| OutputTensor | Output | 4 | INT8, UINT8 |
