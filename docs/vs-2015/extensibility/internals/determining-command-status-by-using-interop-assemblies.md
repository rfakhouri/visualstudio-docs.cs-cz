---
title: Určení stavu příkazu pomocí spolupracujícího sestavení | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 22648a85f8c8774896914b9519aa3d10d3dc732d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670181"
---
# <a name="determining-command-status-by-using-interop-assemblies"></a>Určení stavu příkazu pomocí definičních sestavení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [určení příkaz stav podle pomocí zprostředkovatele komunikace s objekty sestavení](https://docs.microsoft.com/visualstudio/extensibility/internals/determining-command-status-by-using-interop-assemblies).  
  
VSPackage musí udržovat přehled o stavu příkazy, které dokáže zpracovat. Prostředí nelze určit, když se stane příkaz zpracovávají v rámci vašeho balíčku VSPackage povoleno nebo zakázáno. Je zodpovědností vašeho balíčku VSPackage informovat o stavech příkazového prostředí, například stav Obecné příkazy, jako **Vyjmout**, **kopírování**, a **vložit**.  
  
## <a name="status-notification-sources"></a>Stav oznámení zdroje  
 Prostředí obdrží informace o příkazech prostřednictvím rozšíření VSPackages' <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metodu, která je součástí sady VSPackage implementace nástroje <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní. Prostředí volá <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda VSPackage pod dvě podmínky:  
  
-   Když uživatel otevře hlavní nabídky nebo místní nabídku (kliknutím pravým tlačítkem myši), spustí prostředí <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda u všech příkazů v této nabídce k určení stavu.  
  
-   Když sady VSPackage požádá, že prostředí aktualizovat aktuální uživatelské rozhraní (UI). V takovém jako příkazy, které jsou aktuálně viditelné pro uživatele, jako je například **Vyjmout**, **kopírování**, a **vložit** seskupování na standardním panelu nástrojů, budou povolené i zakázané v odpovědi na akce kontextu a uživatele.  
  
 Protože prostředí hostitelem více rozšíření VSPackages, výkon k prostředí by nepřijatelně snížit, pokud bylo potřeba dotazovat každou VSPackage k určení stavu příkazu. Místo toho vaše VSPackage aktivně oznámí prostředí při změně jeho uživatelského rozhraní za čas změny. Další informace o oznámení o aktualizaci, najdete v části [aktualizaci uživatelského rozhraní](../../extensibility/updating-the-user-interface.md).  
  
## <a name="status-notification-failure"></a>Chyba stavu oznámení  
 Selhání vašeho balíčku VSPackage oznámit prostředí změnu stavu příkazu můžete umístit uživatelského rozhraní v nekonzistentním stavu. Mějte na paměti, že všechny příkazy vaše nabídky nebo kontext mohou být umístěny na panelu nástrojů uživatelem. Proto pouze v případě, že se otevře nabídka nebo místní nabídka aktualizace uživatelského rozhraní není dost.  
  
## <a name="see-also"></a>Viz také  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementace](../../extensibility/internals/command-implementation.md)

