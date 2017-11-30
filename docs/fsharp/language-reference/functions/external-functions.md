---
title: "Dış İşlevler (F#)"
description: "Yerel kodda işlevleri çağırmak için F # dil desteği hakkında bilgi edinin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="527fe-104">Dış İşlevler</span><span class="sxs-lookup"><span data-stu-id="527fe-104">External Functions</span></span>

<span data-ttu-id="527fe-105">Bu konuda yerel kodda işlevleri çağırma F # dili desteği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="527fe-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="527fe-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="527fe-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="527fe-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="527fe-107">Remarks</span></span>

<span data-ttu-id="527fe-108">Önceki sözdiziminde *bağımsız değişkenleri* için sağlanan değişkenlerini temsil eden `System.Runtime.InteropServices.DllImportAttribute` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="527fe-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="527fe-109">İlk bağımsız değişken .dll uzantısı olmadan bu işlevi içeren dll Dosyasının adını temsil eden bir dizedir.</span><span class="sxs-lookup"><span data-stu-id="527fe-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="527fe-110">Ek bağımsız değişkenler sağlanan herhangi bir ortak özellikleri için `System.Runtime.InteropServices.DllImportAttribute` çağırma gibi sınıfı.</span><span class="sxs-lookup"><span data-stu-id="527fe-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="527fe-111">Yerel C++ aşağıdaki dışarı aktarılan işlevi içeren DLL olduğunu varsayın.</span><span class="sxs-lookup"><span data-stu-id="527fe-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="527fe-112">Bu işlev F # aşağıdaki kodu kullanarak çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="527fe-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="527fe-113">Yerel kod ile birlikte çalışabilirlik olarak adlandırılır *platform çağırma* ve CLR özelliğidir.</span><span class="sxs-lookup"><span data-stu-id="527fe-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="527fe-114">Daha fazla bilgi için bkz: [yönetilmeyen kod ile birlikte çalışma](https://msdn.microsoft.com/library/sd10k43k.aspx).</span><span class="sxs-lookup"><span data-stu-id="527fe-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="527fe-115">Bu bölümdeki bilgiler, F # için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="527fe-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="527fe-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="527fe-116">See Also</span></span>

[<span data-ttu-id="527fe-117">İşlevler</span><span class="sxs-lookup"><span data-stu-id="527fe-117">Functions</span></span>](index.md)