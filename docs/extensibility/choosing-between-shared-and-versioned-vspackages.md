---
title: Volba mezi sdílené a verzí VSPackages | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- SxS
- side-by-side installation
- installation [Visual Studio SDK], side-by-side
ms.assetid: e3128ac3-2e92-48e9-87ab-3b6c9d80e8c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ce7f58d664c6a186146272af16324be2fee90983
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31104615"
---
# <a name="choosing-between-shared-and-versioned-vspackages"></a>Volba mezi VSPackages sdílené a verzí
Různé verze sady Visual Studio mohou existovat vedle sebe na stejném počítači. VSPackages může podporovat všechny směs [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] verze.  
  
 Můžete povolit souběžně sdílená instalace VSPackages prostřednictvím buď dva strategie, sdílené strategie nebo verzí strategie. Obě zohlednit přítomnost více verzí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a přidružené verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
 Ve sdílené strategii jeden VSPackage je zaregistrovaný pro použití v různých verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. V verzí strategie, jsou nainstalované knihovny DLL více VSPackage, jeden pro každou verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , které podporujete.  
  
## <a name="shared-vspackages"></a>Sdílené VSPackages  
 Použití sdílené VSPackage je vhodné, když používají stejné VSPackage v různých verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. K implementaci sdílené VSPackage, musíte provést následující kroky:  
  
-   Aby vaše VSPackage kompatibilní s více verzemi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Dva způsoby provádění takže jsou k dispozici:  
  
    -   Omezit vaše VSPackage pomocí pouze funkce nejdřívější verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , které podporujete.  
  
    -   Program vaše VSPackage přizpůsobit na verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve kterém je spuštěná. Poté, v případě dotazů pro novější služby selžou, vaše VSPackage nabízejí jiných služeb, které jsou podporovány ve starších verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Zaregistrujte vaše VSPackage správně. Další informace najdete v tématu [VSPackage registrace](../extensibility/internals/vspackage-registration.md) a [spravované registrace VSPackage](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1).  
  
-   Přípony souborů zaregistrujte správně. Další informace najdete v tématu [registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).  
  
-   Vytvořit instalační program, který nasadí vaši VSPackage pro příslušné verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [instalaci VSPackages pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md) a [správu součástí](../extensibility/internals/component-management.md).  
  
-   Vyřešte problém kolizí registrace. Další informace najdete v tématu [VSPackage registrace](../extensibility/internals/vspackage-registration.md).  
  
-   Ujistěte se, že sdílené a verzí souborů respektují umožňuje bezpečné instalaci a odebrání více verzí při počítání referencí. Další informace najdete v tématu [správu součástí](../extensibility/internals/component-management.md).  
  
## <a name="versioned-vspackages"></a>Verzí VSPackages  
 V rámci verzí VSPackage strategie, vytvoříte jeden VSPackage pro každou verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , které podporujete. To je vhodné, pokud chcete využít výhod služeb poskytovaných novější verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], protože každý VSPackage můžete rozvíjet bez vlivu jiné. Nicméně verzí strategie vytváření více binární soubory z jednotného kódu nebo z několika základů kódu nezávislé, může za následek další počáteční vývoj než sdílené strategie. Další nastavení pracovní můžou také požadovat, protože musíte vytvořit buď samostatný instalační program pro každou verzi nebo jednoho instalačního programu, která zjistí verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , které se nainstalují, a že vaše VSPackage podporuje.  
  
## <a name="binary-compatibility"></a>Binární kompatibilitu  
 Obecně platí binární kompatibilitu umožňuje nativního kódu VSPackages vytvořených v dřívějších verzích sady Visual Studio spustit v novějších verzích sady Visual Studio. Existují však tři důležité výjimky:  
  
-   Pokud vaše VSPackage spoléhá na konkrétní verzi modulu CLR, pak musí určit v různých verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je spuštěná.  
  
-   VSPackage může mít závislost na konkrétní funkci jiné VSPackage nebo jiného produktu. V důsledku toho VSPackage můžete spustit pouze kde uspokojit závislost.  
  
-   VSPackage může být ovlivněn opravu zabezpečení v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] aktualizace service pack nebo novější verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. V takových případech VSPackage vytvořených v dřívější verzi [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] nemusí být možné spustit ve verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] po opravu zabezpečení. Můžete však sestavte svůj balíček pomocí novější verze znovu a mít ji taky spustit ve starších verzích.  
  
 Spravované VSPackages musí být vytvořená s využitím verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] a [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] odpovídající cílovou verzi sady [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Kromě plánování binární kompatibilitu pro vaše VSPackage binární soubory, můžete také měli zvažte řešení a projektu formáty souborů. Pokud vaše VSPackage vytvoří nový typ projektu, je nutné rozhodnout, jestli může spustit v právě jednu verzi nebo v různých verzích [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [upgrade projektů vlastní](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects).  
  
## <a name="see-also"></a>Viz také  
 [Instalace VSPackages pomocí Instalační služby systému Windows](../extensibility/internals/installing-vspackages-with-windows-installer.md)   
 [Správa komponent](../extensibility/internals/component-management.md)