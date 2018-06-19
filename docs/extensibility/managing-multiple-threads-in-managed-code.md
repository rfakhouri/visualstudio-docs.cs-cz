---
title: 'Postupy: Správa více vláken ve spravovaném kódu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 59730063-cc29-4dae-baff-2234ad8d0c8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c0888a0f65f36d624deffac60ceee032d3f3d13a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139663"
---
# <a name="how-to-managing-multiple-threads-in-managed-code"></a>Postupy: Správa více vláken ve spravovaném kódu
Pokud máte spravované VSPackage rozšíření, které volá asynchronní metody, nebo se operace, které jsou spouštěny na vláken než vlákna uživatelského rozhraní Visual Studio, postupujte podle níže uvedených pokynů. Vlákna uživatelského rozhraní můžete zachovat reakce, protože není třeba čekat pro práci na jiné vlákno k dokončení. Můžete provést kódu efektivnější, protože nemáte navíc vláken, které zabírají prostor v zásobníku, a je možné provádět spolehlivější a snazší ladění, protože se vyhnout blokování a zablokování.  
  
 Obecně platí, můžete přepnout z vlákna uživatelského rozhraní na jiné vlákno nebo naopak. Po návratu metody, je aktuální vlákno vlákno, odkud byla původně volána.  
  
> [!IMPORTANT]
>  Tyto pokyny použijte rozhraní API v <xref:Microsoft.VisualStudio.Threading> obor názvů, zejména <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> třídy. Rozhraní API v tomto oboru názvů jsou v nové [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)]. Můžete získat instanci <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> z <xref:Microsoft.VisualStudio.Shell.ThreadHelper> vlastnost `ThreadHelper.JoinableTaskFactory`.  
  
## <a name="switching-from-the-ui-thread-to-a-background-thread"></a>Přepnutí z vlákna uživatelského rozhraní do vlákna na pozadí  
  
1.  Pokud jste ve vlákně UI a chcete provést asynchronní u vlákna na pozadí, použijte Task.Run():  
  
    ```csharp  
    await Task.Run(async delegate{  
        // Now you're on a separate thread.  
    });  
    // Now you're back on the UI thread.  
  
    ```  
  
2.  Pokud jste ve vlákně UI a chcete zablokovat synchronně během provádění pracovní na vlákna na pozadí, použijte <xref:System.Threading.Tasks.TaskScheduler> vlastnost `TaskScheduler.Default` uvnitř <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>:  
  
    ```csharp  
    // using Microsoft.VisualStudio.Threading;  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        await TaskScheduler.Default;  
        // You're now on a separate thread.  
        DoSomethingSynchronous();  
        await OrSomethingAsynchronous();  
    });  
    ```  
  
## <a name="switching-from-a-background-thread-to-the-ui-thread"></a>Přepnutí z vlákna na pozadí na vlákna uživatelského rozhraní  
  
1.  Pokud jste v vlákna na pozadí a chcete udělat něco ve vlákně UI, použijte <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>:  
  
    ```csharp  
    // Switch to main thread  
    await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
    ```  
  
     Můžete použít <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> metoda přepnout do vlákna uživatelského rozhraní. Tato metoda odešle zprávu do vlákna uživatelského rozhraní s pokračování aktuální asynchronní metody a taky komunikuje s ostatními vláken framework nastavit správné prioritu a zamezit tak zablokování.  
  
     Pokud není asynchronní metodu pozadí přístup z více vláken a nemůžete ji asynchronní, můžete dál používat `await` syntaxe přepnout do vlákna uživatelského rozhraní pomocí zabalení práci s <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>, protože v tomto příkladu:  
  
    ```csharp  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        // Switch to main thread  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        // Do your work on the main thread here.  
    });  
    ```