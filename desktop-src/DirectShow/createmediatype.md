---
Description: The CreateMediaType function allocates a new AM\_MEDIA\_TYPE structure, including the format block.
ms.assetid: 841a8c51-6027-49d6-b3d8-b5e21e3d5f13
title: CreateMediaType function
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# CreateMediaType function

The **CreateMediaType** function allocates a new [**AM\_MEDIA\_TYPE**](/windows/desktop/api/strmif/ns-strmif-_ammediatype) structure, including the format block.

## Syntax


```C++
AM_MEDIA_TYPE* WINAPI CreateMediaType(
   AM_MEDIA_TYPE const *pSrc
);
```



## Parameters

<dl> <dt>

*pSrc* 
</dt> <dd>

Pointer to an [**AM\_MEDIA\_TYPE**](/windows/desktop/api/strmif/ns-strmif-_ammediatype) structure. The method copies this structure into the new structure.

</dd> </dl>

## Return value

Returns a new [**AM\_MEDIA\_TYPE**](/windows/desktop/api/strmif/ns-strmif-_ammediatype) structure, or **NULL** if there is an error.

## Remarks

To free the memory allocated by this function, call [**DeleteMediaType**](deletemediatype.md).

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Mtype.h (include Streams.h)</dt> </dl>                                                                                     |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**Media Type Functions**](media-type-functions.md)
</dt> </dl>

 

 



