---
title: 'Postupy: určení umístění souboru se symboly z příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf6c17430c4f56ae1821a149d4a7cc5f82f0028e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571427"
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Postupy: určení umístění souboru se symboly z příkazového řádku
K zobrazení informací o symbolu například názvy funkcí a čísla řádků, vsperfreport – nástroj příkazového řádku vyžaduje přístup k symbolu (. *pdb*) soubory PROFILOVANÉHO součásti a soubory systému Windows. Symbol soubory se vytvoří při kompilaci komponentu. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md). Vsperfreport – automaticky vyhledá soubory symbolů v následujících umístěních:  
  
-   Cesty zadané v **/SymbolPath** možnost nebo **_NT_SYMBOL_PATH** proměnné prostředí.  
  
-   Přesný místní cesta kde byl kompilován komponentu.  
  
-   Adresář, který obsahuje data profilování (. *Vsp* nebo. *vsps*) souboru.  
  
 Společnost Microsoft poskytuje. *pdb* soubory pro řadu jeho produktů online na serveru symbol. Pokud počítač, který používáte pro vytváření sestav je připojený k Internetu, vsperfreport – připojí k serveru online symbol automaticky vyhledat informací o symbolu a ukládat soubory do místního úložiště.  
  
 Umístění symbolu soubory a úložišti Microsoft symbol serveru můžete zadat následujícími způsoby:  
  
-   Nastavte **_NT_SYMBOL_PATH** proměnné prostředí.  
  
-   Přidat **/SymbolPath** možnost vsperfreport – příkazový řádek.  
  
 Můžete také použít obě tyto metody.  
  
> [!NOTE]
>  Pokud [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalován v místním počítači, do umístění pro soubory symbolů Windows pravděpodobně byla zadána již. Další informace najdete v tématu [postupy: odkaz na Windows symbolů informace](../profiling/how-to-reference-windows-symbol-information.md). Ale stejně musí nakonfigurovat vsperfreport – pro umístění a serveru, jak je popsáno dále v tomto tématu.  
  
## <a name="specify-windows-symbol-files"></a>Zadejte soubory Windows symbolů  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>Můžete konfigurovat použití systému Windows server – symbol  
  
1.  V případě potřeby vytvořte adresář k uložení souborů symbol místně.  
  
2.  Použijte následující syntaxi nastavit **_NT_SYMBOL_PATH** proměnné prostředí nebo možnost /SymbolPath vsperfreport –:  
  
     **SRV\***  *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
     kde *LocalStore* je cesta místní adresář, který jste vytvořili.  
  
## <a name="specify-component-symbol-files"></a>Zadejte soubory symbolů součásti  
 Profilace nástrojů pro vyhledávání. *pdb* soubory součástí, které chcete profil do jejich původního umístění, které jsou uložené v součásti nebo ve složce, která obsahuje soubor profilování data. Můžete určit jiné umístění pro vyhledávání můžete přidat jeden nebo více cest k **_NT_SYMBOL_PATH** nebo **/SymbolPath** možnost. Samostatné cesty oddělte středníky.  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek sady **_NT_SYMBOL_PATH** proměnnou prostředí na Windows server symbol a místní adresář, který má **C:\Symbols**.  
  
 **nastavit _NT_SYMBOL_PATH = srv\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Následující příkazový řádek vsperfreport – přidá C:\Projects\Symbols adresář do cesty vyhledávání pomocí **/SymbolPath** možnost.  
  
 **Vsperfreport –***Moje aplikace* **.exe /SymbolPath:C:\Projects\Symbols /summary:all**