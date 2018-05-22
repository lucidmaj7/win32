---
title: NM\_RCLICK (toolbar) notification code
description: Sent by a toolbar control when the user clicks the toolbar with the right mouse button. This notification code is sent in the form of a WM\_NOTIFY message.
ms.assetid: 'e9d2d871-e922-444d-a76c-e73f249ed410'
keywords: ["NM_RCLICK (toolbar) notification code Windows Controls"]
topic_type:
- apiref
api_name:
- NM_RCLICK
api_location:
- Commctrl.h
api_type:
- HeaderDef
---

# NM\_RCLICK (toolbar) notification code

Sent by a toolbar control when the user clicks the toolbar with the right mouse button. This notification code is sent in the form of a [**WM\_NOTIFY**](wm-notify.md) message.


```C++
NM_RCLICK

    lpnmmouse = (LPNMMOUSE) lParam;
```



## Parameters

<dl> <dt>

*lParam* 
</dt> <dd>

Pointer to an [**NMMOUSE**](nmmouse.md) structure that contains information about this notification code. If the mouse was clicked on a toolbar item, the **dwItemSpec** member contains the item identifier and the **dwItemData** member contains the item data. If the mouse was clicked on a separator or white space in the toolbar, the **dwItemSpec** member will contain -1.

</dd> </dl>

## Return value

Returns **FALSE** to allow the toolbar control to perform default processing of the event, or **TRUE** to prevent the control from processing the event.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Commctrl.h</dt> </dl> |



�

�




