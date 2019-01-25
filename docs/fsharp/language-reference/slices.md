---
title: Slices (F#)
description: Erfahren Sie, wie Sie mit Slices für bestehende F# -Datentypen und wie Sie Ihre eigenen Slices für andere Datentypen zu definieren.
ms.date: 01/22/2019
ms.openlocfilehash: c204c6cbb195b33998b92dd940313a132ecc321d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746707"
---
# <a name="slices"></a><span data-ttu-id="77806-103">Slices</span><span class="sxs-lookup"><span data-stu-id="77806-103">Slices</span></span>

<span data-ttu-id="77806-104">In F#, ein Slice ist eine Teilmenge von einem Datentyp.</span><span class="sxs-lookup"><span data-stu-id="77806-104">In F#, a slice is a subset of a data type.</span></span> <span data-ttu-id="77806-105">Um einen Slice von einem Datentyp werden können, der Datentyp muss entweder definieren eine `GetSlice` Methode oder in eine ["Erweiterung"](type-extensions.md) , im Bereich.</span><span class="sxs-lookup"><span data-stu-id="77806-105">To be able to take a slice from a data type, the data type must either define a `GetSlice` method or in a [type extension](type-extensions.md) that is in scope.</span></span> <span data-ttu-id="77806-106">In diesem Artikel wird erläutert, wie Slices aus vorhandenen F# Typen und wie Sie Ihre eigenen definieren.</span><span class="sxs-lookup"><span data-stu-id="77806-106">This article explains how to take slices from existing F# types and how to define your own.</span></span>

<span data-ttu-id="77806-107">Slices ähneln [Indexer](members/indexed-properties.md), jedoch anstelle der Rückgabe eines einzelnen Werts aus der zugrunde liegende Datenstruktur, mehrere zu.</span><span class="sxs-lookup"><span data-stu-id="77806-107">Slices are similar to [indexers](members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="77806-108">F#derzeit verfügt über systeminterne Unterstützung für das Aufteilen von Zeichenfolgen, Listen, Arrays und Direct2D-Arrays.</span><span class="sxs-lookup"><span data-stu-id="77806-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="77806-109">Grundlegende Aufteilen in Slices mit F# Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="77806-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="77806-110">Die am häufigsten verwendeten Datentypen, die in Slices aufgeteilt werden sind F# Listen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="77806-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="77806-111">Im folgenden wird veranschaulicht, wie Sie dies mit Listen:</span><span class="sxs-lookup"><span data-stu-id="77806-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="77806-112">Aufteilen in Slices Arrays ist, genau wie das Aufteilen in Slices aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="77806-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="77806-113">Segmentieren von mehrdimensionalen arrays</span><span class="sxs-lookup"><span data-stu-id="77806-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="77806-114">F#mehrdimensionale Arrays in unterstützt die F# -Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="77806-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="77806-115">Wie bei eindimensionalen Arrays können Segmente der mehrdimensionalen Arrays auch nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="77806-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="77806-116">Allerdings erfordert die Einführung von zusätzliche Dimensionen eine etwas andere Syntax, damit Sie die Slices von bestimmten Zeilen und Spalten nutzen können.</span><span class="sxs-lookup"><span data-stu-id="77806-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="77806-117">Die folgenden Beispiele veranschaulichen, wie Sie einem 2D-Array unterteilen:</span><span class="sxs-lookup"><span data-stu-id="77806-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twobyTwo
```

<span data-ttu-id="77806-118">Die F# Core-Bibliothek definiert keine `GetSlice`für 3D Arrays.</span><span class="sxs-lookup"><span data-stu-id="77806-118">The F# core library does not define `GetSlice`for 3D arrays.</span></span> <span data-ttu-id="77806-119">Wenn Sie diese oder andere Arrays mit mehr Dimensionen in Slices aufteilen möchten, müssen Sie definieren die `GetSlice` Element selbst.</span><span class="sxs-lookup"><span data-stu-id="77806-119">If you wish to slice those or other arrays of more dimensions, you must define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="77806-120">Definieren von Slices für andere Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="77806-120">Defining slices for other data structures</span></span>

<span data-ttu-id="77806-121">Die F# Segmente für einen begrenzten Satz von Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="77806-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="77806-122">Wenn Sie die Slices für mehr Datentypen definieren möchten, können Sie entweder in die Typdefinition selbst oder in einer typerweiterung dafür.</span><span class="sxs-lookup"><span data-stu-id="77806-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="77806-123">Beispielsweise sieht wie Sie die Slices für definieren können die <xref:System.ArraySegment`1> Klasse, um die einfache datenbearbeitung zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="77806-123">For example, here's how you might define slices for the <xref:System.ArraySegment`1> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="77806-124">Um Boxing zu vermeiden, sollte es nötig inlining verwenden</span><span class="sxs-lookup"><span data-stu-id="77806-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="77806-125">Wenn Sie Segmente für einen Typ, die tatsächlich eine Struktur ist definieren, wird empfohlen, die Sie `inline` der `GetSlice` Member.</span><span class="sxs-lookup"><span data-stu-id="77806-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="77806-126">Die F# Compiler optimiert die optionalen Argumente, die jegliche Heapzuweisungen durch das Aufteilen in Slices zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="77806-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="77806-127">Dies ist sehr wichtig für das Segmentieren von Konstrukten wie z. B. <xref:System.Span`1> , die nicht zugeordnet werden können werden auf dem Heap.</span><span class="sxs-lookup"><span data-stu-id="77806-127">This is critically important for slicing constructs such as <xref:System.Span`1> that cannot be be allocated on the heap.</span></span>

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a><span data-ttu-id="77806-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77806-128">See also</span></span>

- [<span data-ttu-id="77806-129">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="77806-129">Indexed properties</span></span>](members/indexed-properties.md)