---
title: 'Spravované ladění: Doporučené nastavení vlastností | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], managed
- debugging managed code, recommended property settings
ms.assetid: 3d14a8d4-2925-44d0-be41-ec546d411db9
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f63e1382d242a679ed4fac09bfb3040200fed551
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797815"
---
# <a name="managed-debugging-recommended-property-settings"></a>Spravované ladění: Doporučené nastavení vlastností
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určité vlastnosti měly být nastaveny stejným způsobem jako pro všechny spravované scénáře ladění.  
  
 Následující tabulky obsahují doporučené nastavení vlastností.  
  
 Nastavení, které tu nejsou uvedené, mohou lišit mezi různými typy spravovaných projektů. Například **spustit akci** bude nastaveno jinak v projektu Windows Forms než [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] projektu.  
  
### <a name="configuration-properties-on-the-build-c-or-compile-visual-basic-tab"></a>Vlastnosti konfigurace na kartě sestavení (C#) nebo kompilace (Visual Basic)  
  
|**Název vlastnosti**|**Nastavení**|  
|-----------------------|-----------------|  
|**Definovat konstantu DEBUG**|C#a F#: Zaškrtávací políčko vráceny. To umožňuje vaší aplikaci použít třídu ladění.|  
|**Definovat konstantu TRACE**|C#a F#: Zaškrtávací políčko vráceny. To umožňuje vaší aplikaci použít třídu trasování.|  
|**Optimalizovat kód**|C#, F#and Visual Basic: Nastavte na hodnotu false. Optimalizovaný kód je těžší ladit, protože generované pokyny neodpovídají přímo ke zdrojovému kódu. Pokud zjistíte, váš program obsahuje chybu, která se zobrazí pouze v optimalizovaném kódu, můžete zapnout toto nastavení, ale mějte na paměti, že kód zobrazený v **zpětný překlad** okna je generován z optimalizovaného zdrojového, který se nemusí shodovat, co se zobrazí v kódu Editor. Chcete-li ladit optimalizovaný kód, musíte vypnout [pouze můj kód](just-my-code.md).<br /><br /> Další informace najdete v tématu [nastavení projektu pro ladění konfigurace jazyka C#](../debugger/project-settings-for-csharp-debug-configurations.md) nebo [nastavení projektu pro konfiguraci ladění jazyka Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).|  
|**Výstupní cesta**|Nastavte na bin\Debug\\.|  
|**Možnosti rozšířené kompilace**|Pouze v jazyce Visual Basic. Klikněte na tlačítko **Upřesnit** nastavit rozšířené vlastnosti, které jsou popsány v následující tabulce.|  
  
### <a name="advanced-compiler-settings-dialog-box"></a>dialogové okno Upřesnit nastavení kompilátoru  
  
|**Název vlastnosti**|**Nastavení**|  
|-----------------------|-----------------|  
|**Povolit optimalizace**|Nastavte na hodnotu false z důvodů uvedených v **optimalizovat kód** možnost v předchozí tabulce.|  
|**Generovat ladicí informace**|Toto políčko zaškrtněte způsobit příznak/Debug bude nastaven při kompilaci, která bude generovat informace potřebné k usnadnění ladění.|  
|**Definovat konstantu DEBUG**|Zaškrtněte toto políčko, chcete-li definovat `DEBUG` – konstanta, která umožňuje aplikacím používat <xref:System.Diagnostics.Debug> třídy.|  
|**Definovat konstantu TRACE**|Zaškrtněte toto políčko, chcete-li definovat `TRACE` – konstanta, která umožňuje aplikacím používat <xref:System.Diagnostics.Trace> třídy.|  
  
## <a name="see-also"></a>Viz také  
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)   
 [Typy projektů jazyka C#, F# a Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)
