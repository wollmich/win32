---
title: JET_PFNREALLOC Callback Function
TOCTitle: JET_PFNREALLOC Callback Function
ms:assetid: 443d0b7e-1c3b-4584-9bc3-938724527313
ms:mtpsurl: https://msdn.microsoft.com/library/Gg269237(v=EXCHG.10)
ms:contentKeyID: 32765539
ms.date: 04/11/2016
ms.topic: reference
api_name: 
topic_type: 
- apiref
- kbArticle
api_type: 
- COM
api_location: 
ROBOTS: INDEX,FOLLOW

---

# JET_PFNREALLOC Callback Function


_**Applies to:** Windows | Windows Server_

## JET_PFNREALLOC Callback Function

The JET_PFNREALLOC function is a [realloc](https://msdn.microsoft.com/library/xbebcx7d.aspx) compatible callback used by [JetEnumerateColumns](gg269321\(v=exchg.10\).md) to allocate memory for its output buffers.

```cpp
    void * JET_API JET_PFNREALLOC(
      [in]                 void* pvContext,
      [in]                 void* pv,
      [in]                 unsigned long cb
    );
```

### Parameters

*pvContext*

The context pointer given to [JetEnumerateColumns](gg269321\(v=exchg.10\).md). This context pointer can be used to convey state from the caller of [JetEnumerateColumns](gg269321\(v=exchg.10\).md) to the implementation of this callback.

*pv*

If non-NULL, specifies a pointer to a memory block previously allocated by this callback. If NULL, a new memory block of the requested size will be allocated.

*cb*

The new size of the memory block in bytes. If this parameter is 0 (zero) and a memory block is specified, that memory block will be freed.

### Return Value

The system may generate success or failure codes as a result of a call to this function. For information about how to return these codes as HRESULTs, see [Extensible Storage Engine Errors](gg269184\(v=exchg.10\).md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Return code</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Success</p></td>
<td><p>If a previously allocated memory block was specified and a new size of zero was specified then that block is freed and NULL will be returned. If a previously allocated memory block was specified and a non-zero new size was specified then the reallocated memory block is returned. If no memory block was specified then a newly allocated memory block of the specified size is returned.</p></td>
</tr>
<tr class="even">
<td><p>Failure</p></td>
<td><p>NULL will be returned. If a previously allocated memory block was provided then that block will remain allocated.</p></td>
</tr>
</tbody>
</table>


### Requirements

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Client</strong></p></td>
<td><p>Requires Windows Vista, Windows XP, or Windows 2000 Professional.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Requires Windows Server 2008, Windows Server 2003, or Windows 2000 Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Header</strong></p></td>
<td><p>Declared in Esent.h.</p></td>
</tr>
</tbody>
</table>


### See Also

[JetEnumerateColumns](gg269321\(v=exchg.10\).md)

