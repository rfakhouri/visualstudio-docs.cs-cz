---
title: Příkaz umístění pokyny | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c406a5a34ea2556d367c8f7af8a9fda70fcc2676
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134457"
---
# <a name="command-placement-guidelines"></a>Příkaz umístění pokyny
Osvědčené postupy pro umístění příkazy v sadě Visual Studio integrované vývojové prostředí (IDE) se liší v závislosti na velikosti sadu příkazů. Příkazy jsou definováni a umístí podle informací v souborech .vsct.  
  
## <a name="best-practices-for-all-command-sets"></a>Osvědčené postupy pro všechny sady příkazů  
 Pro každou sadu příkazů postupujte podle následujících pokynů:  
  
-   Graf struktury příkaz připravte předem. Identifikujte příkazy, pole se seznamem, příkaz skupiny a místní nabídky, které se použijí na více než jednom místě.  
  
-   Příkazy, které se zobrazují ve stejné skupině by měl mít relaci.  
  
-   Skupiny, které obsahují pouze jeden příkaz jsou přijatelné.  
  
-   Balíčky neměli přidávat spoustu příkazy nabídky existující sady Visual Studio. Místo toho by měl vytvořit nabídky nebo dílčích pro hostování nové příkazy.  
  
-   Když vložíte příkaz na existující nabídky, název příkaz tak, aby jejím účelem je zrušte a nebude Nezaměňovat s existující příkazy.  
  
## <a name="best-practices-for-small-command-sets"></a>Osvědčené postupy pro malé příkaz sady  
 Pokud vyvíjíte VSPackage s několika příkazů, také postupujte podle těchto pokynů:  
  
-   Pokud je to možné, použijte [nadřazený Element](../../extensibility/parent-element.md) příkaz, pole se seznamem, skupiny, nebo nabídky podřízené uvést do příslušné skupiny.  
  
-   Tyto skupiny přiřadíte zobrazuje VSPackage nabídky.  
  
-   Musí být Nadřazená podřízené nabídky nebo příkaz [skupinového elementu](../../extensibility/group-element.md). Příkazy a podřízené nabídky přiřadit skupiny a potom přiřadit nabídky nadřazené skupiny.  
  
-   Příkaz můžete umístit do další skupiny přidáním [CommandPlacements Element](../../extensibility/commandplacements-element.md) části po definici příkazu a přidáním do `CommandPlacements Element` [CommandPlacement Element](../../extensibility/commandplacement-element.md) pro každou Další skupiny.  
  
## <a name="best-practices-for-large-command-sets"></a>Osvědčené postupy pro příkaz velké sady  
 Pokud vaše VSPackage bude mít mnoho příkazy, které se zobrazí v několika kontextech, také postupujte podle následujících pokynů:  
  
-   Ujistěte se, nabídek, skupiny a příkazy Samoobslužná správa nadřazených. To znamená, nepřiřazujte `Parent Element` v definici položky.  
  
-   Použití `CommandPlacement Element` položek v `CommandPlacements Element` části uvést nabídek, skupiny a příkazy do své nadřazené nabídky a skupiny.  
  
-   V `CommandPlacements` část, položky, které naplnit dané nabídky nebo skupiny by měly být vedle sebe navzájem. To je výhodné čitelnost a umožňuje `Priority` usnadňují určení pořadí.  
  
## <a name="see-also"></a>Viz také  
 [Jak přidat VSPackages prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)