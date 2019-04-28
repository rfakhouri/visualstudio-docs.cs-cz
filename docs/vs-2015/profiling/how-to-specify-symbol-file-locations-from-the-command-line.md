---
title: 'Postupy: Zadejte umístění souborů se symboly z příkazového řádku | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e5ff4290d0cffa99a9f476c543626c5aa15be87a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436914"
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Postupy: Zadejte umístění souborů se symboly z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vsperfreport – nástroj příkazového řádku k zobrazení informací o symbolu, jako jsou názvy funkcí a čísla řádků, vyžaduje přístup k soubory symbolů (PDB) PROFILOVANÉHO komponent a souborů systému Windows. Soubory symbolů se vytvoří při kompilaci komponentu. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md). VSPerfReport automaticky vyhledá soubory symbolů v následujících umístěních:  
  
- Cesty zadané **/symbolpath** možnost nebo v **_NT_SYMBOL_PATH** proměnné prostředí.  
  
- Přesné místní cesta kde byl zkompilován komponentu.  
  
- Adresář obsahující soubor dat profilování (.vsp nebo .vsps).  
  
  Společnost Microsoft poskytuje soubory s příponou .pdb pro spoustu jejích produktů online na serveru symbolů. Pokud počítač, který používáte pro vytváření sestav je připojený k Internetu, VSPerfReport připojí k serveru symbolů online automaticky vyhledat informace o symbolech a uložte soubory do místního úložiště.  
  
  Zadejte umístění souborů symbolů a úložišti Microsoft symbol server následujícími způsoby:  
  
- Nastavte **_NT_SYMBOL_PATH** proměnné prostředí.  
  
- Přidat **/symbolpath** možnost příkazového řádku VSPerfReport.  
  
  Můžete také použít obě tyto metody.  
  
> [!NOTE]
> Pokud [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] je nainstalována na místním počítači, do umístění pro soubory symbolů Windows pravděpodobně nebyl zadán již. Další informace najdete v tématu [jak: Informace o symbolech Windows odkaz](../profiling/how-to-reference-windows-symbol-information.md). Stále musíte nakonfigurovat nastavení nástroje VSPerfReport pro umístění a serveru, jak je popsáno dále v tomto tématu.  
  
## <a name="specifying-windows-symbol-files"></a>Zadat soubory symbolů Windows  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>Můžete konfigurovat použití Windows serveru symbolů  
  
1. V případě potřeby vytvořte adresář pro uložení souborů symbolů místně.  
  
2. Použijte následující syntax k nastavení **_NT_SYMBOL_PATH** proměnné prostředí nebo možnost VSPerfReport/symbolpath:  
  
    **srv\\*** *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
    kde *LocalStore* je cesta k místnímu adresáři, který jste vytvořili.  
  
## <a name="specifying-component-symbol-files"></a>Určení souborů symbolů komponenty  
 Profilování nástroje hledá soubory the.pdb komponent, které chcete do profilu do jejich původního umístění, které jsou uloženy v součásti nebo ve složce, která obsahuje soubor dat profilování. Můžete zadat jiné umístění pro hledání tak, že přidáte jednu nebo více cest k **_NT_SYMBOL_PATH** nebo **/symbolpath** možnost. Samostatné cesty oddělte středníkem.  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek sady **_NT_SYMBOL_PATH** proměnnou prostředí pro Windows server symbolů a místní adresář, do **C:\Symbols**.  
  
 **set  _NT_SYMBOL_PATH=srv\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 Následující příkaz VSPerfReport přidá C:\Projects\Symbols adresář do cesty pro hledání pomocí **/symbolpath** možnost.  
  
 **VSPerfReport**  *MyApp* **.exe /SymbolPath:C:\Projects\Symbols /summary:all**
