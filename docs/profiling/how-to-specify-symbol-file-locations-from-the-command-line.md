---
title: "Postupy: určení umístění souboru se symboly z příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4d0e04c439f5e677cbbbdcfcf560ec976c6257b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Postupy: Určení umístění souboru se symboly z příkazového řádku
Vsperfreport – nástroj příkazového řádku k zobrazení informací o symbolu například názvy funkcí a čísla řádků, vyžaduje přístup k souborům symbolu (.pdb) PROFILOVANÉHO složek a souborů systému Windows. Symbol soubory se vytvoří při kompilaci komponentu. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md). Vsperfreport – automaticky vyhledá soubory symbolů v následujících umístěních:  
  
-   Cesty zadané v **/SymbolPath** možnost nebo **_NT_SYMBOL_PATH** proměnné prostředí.  
  
-   Přesný místní cesta kde byl kompilován komponentu.  
  
-   Adresář, který obsahuje profilování souboru (.vsp nebo .vsps) data.  
  
 Společnost Microsoft poskytuje pro řadu jeho produktů online na serveru symbol soubory PDB. Pokud počítač, který používáte pro vytváření sestav je připojený k Internetu, vsperfreport – připojí k serveru online symbol automaticky vyhledat informací o symbolu a ukládat soubory do místního úložiště.  
  
 Umístění symbolu soubory a úložišti Microsoft symbol serveru můžete zadat následujícími způsoby:  
  
-   Nastavte **_NT_SYMBOL_PATH** proměnné prostředí.  
  
-   Přidat **/SymbolPath** možnost vsperfreport – příkazový řádek.  
  
 Můžete také použít obě tyto metody.  
  
> [!NOTE]
>  Pokud [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalován v místním počítači, do umístění pro soubory symbolů Windows pravděpodobně byla zadána již. Další informace najdete v tématu [postupy: odkaz na informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md). Ale stejně musí nakonfigurovat vsperfreport – pro umístění a serveru, jak je popsáno dále v tomto tématu.  
  
## <a name="specifying-windows-symbol-files"></a>Zadání symbolu soubory systému Windows  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>Můžete konfigurovat použití systému Windows server – symbol  
  
1.  V případě potřeby vytvořte adresář k uložení souborů symbol místně.  
  
2.  Použijte následující syntaxi nastavit **_NT_SYMBOL_PATH** proměnné prostředí nebo možnost /SymbolPath vsperfreport –:  
  
     **SRV\***  *LocalStore*  **\*http://msdl.microsoft.com/downloads/symbols**  
  
     kde *LocalStore* je cesta místní adresář, který jste vytvořili.  
  
## <a name="specifying-component-symbol-files"></a>Zadáte soubory symbolů součásti  
 Profilace nástroje vyhledá soubory the.pdb součástí, které chcete profil do jejich původního umístění, které jsou uložené v součásti nebo ve složce, která obsahuje soubor profilování data. Můžete určit jiné umístění pro vyhledávání můžete přidat jeden nebo více cest k **_NT_SYMBOL_PATH** nebo **/SymbolPath** možnost. Samostatné cesty oddělte středníky.  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek sady **_NT_SYMBOL_PATH** proměnnou prostředí na Windows server symbol a místní adresář, který má **C:\Symbols**.  
  
 **nastavit _NT_SYMBOL_PATH = srv\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Následující příkazový řádek vsperfreport – přidá C:\Projects\Symbols adresář do cesty vyhledávání pomocí **/SymbolPath** možnost.  
  
 **Vsperfreport –***Moje aplikace* **.exe /SymbolPath:C:\Projects\Symbols /summary:all** 