---
title: "Možnosti konfigurace přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project configurations
- configuration options, about configuration options
ms.assetid: f4ad4dd3-b39e-42df-ad89-d403cdf24a2b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0edfe84e26a9331b8c40ec24b00387768bdbba82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-options-overview"></a>Přehled možností konfigurace
Projekty v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] může podporovat víc konfigurací, které mohou být vytvořeny, vyladěnou, spuštění nebo nasazené. Konfigurace je typu sestavení popsané s pojmenovanou sadu vlastností, obvykle přepínače kompilátoru a umístění souborů. Ve výchozím nastavení nová řešení obsahovat dvě konfigurace Debug a Release. Tyto konfigurace provádět pomocí obnoveno výchozí nastavení, nebo upravit tak, aby splňovaly vaše konkrétní požadavky řešení a projektu. Některé balíčky se dají vytvářet dvěma způsoby: jako ActiveX editor nebo jako součást na místě. Projekty pro podporu více konfigurací, ale není nutné. Pokud je dostupný pouze jednu konfiguraci, tato konfigurace je namapována na všechny konfigurace řešení.  
  
 Konfigurace obvykle skládají ze dvou částí – název konfigurace (například ladění a vydání) a nastavení platformy. Název platformy konfigurace identifikuje prostředí, které cíle konfigurace, jako je například rozhraní API nastavit nebo platformu operačního systému. Uživatelé [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] platformu; nelze vytvořit. musíte vybrat z výběr projektu VSPackage umožňuje. Když uživatel nainstaluje VSPackage platformou doručení vytvořit během vývoje balíčku můžete surface libovolný název platformy potřeby založené na všechna kritéria nastavené autorem balíčku. Uživatel pak můžete vybrat ze seznamu platformy, které jsou k dispozici prostřednictvím VSPackage, když jsou vytvářeny instance stránky vlastností.  
  
 Platformy názvy jsou volitelné, protože ne všechny projekty podporují koncept platformy. Při konfiguraci chybí název platformy, řetězec "není k dispozici" se zobrazí v uživatelském rozhraní.  
  
 Každé řešení má svou vlastní sadu konfigurace, pouze jeden z nich může být najednou aktivní. Konfigurace řešení je sada více než jednu konfiguraci z každého projektu. Uvedení "více než" je z důvodu možnost vyloučit projektu z konfigurace řešení. Uživatelé mohou vytvářet své vlastní konfigurace vlastní řešení.  
  
 Následující tabulka ukazuje nastavení typické konfigurace pro projekt. Řádky jsou označeny názvy konfigurace a sloupce s názvy platformy.  
  
|Název konfigurace|Platforma – Win32|Platforma – Win64|  
|------------------------|----------------------|----------------------|  
|Ladit|\<Ladit nastavení Win32 >|\<Ladit nastavení Win64 >|  
|Vydaná verze|\<Verze Win32 Nastavení >|\<Verze Win64 Nastavení >|  
|MyConfig|Není k dispozici|\<Nastavení MyConfig Win64 >|  
  
> [!NOTE]
>  Nelze vytvořit konfiguraci řešení "MyConfig", který vylučuje platformy "Win32" Pokud projektu, které se zaměříte nepodporuje Win32.  
  
 Změna aktivní konfigurace pro řešení vybere sadu konfigurace projektu, které jsou vytvořené, spouštět, ladit nebo nasazení v tomto řešení. Například pokud změníte konfiguraci aktivního řešení z verze pro ladění, všechny projekty v rámci tohoto řešení jsou automaticky vytvořeny s konfigurací projekty, které jsou uvedené v konfiguraci ladění na řešení. Konfigurace projekty jsou obvykle také s názvem ladění pouze tehdy, pokud uživatel má ruční změny v prostředí nástroje Configuration Manager.  
  
 Vlastnosti konfigurace řešení uložené pro každý projekt, patří název projektu, název konfigurace projektu, příznaky indikující, zda se k vytvoření nebo pro nasazení a název platformy. Další informace najdete v tématu [konfigurace řešení](../../extensibility/internals/solution-configuration.md).  
  
 Uživatele můžete zobrazit a nastavit řešení parametry konfigurace výběrem řešení v hierarchii (Průzkumník řešení) a otevření stránek vlastností. Podobně můžete zobrazit a nastavit parametry konfigurace projektu výběrem na projekt v Průzkumníku řešení a otevření stránek vlastností pro tento projekt.  
  
 Uživatele můžete také vytvořit jeden projektu pomocí konfigurace nastavení pro vydání a ostatní konfigurace nastavení pro ladění v případě potřeby. Další informace najdete v tématu [konfigurace projektu pro vytvoření](../../extensibility/internals/project-configuration-for-building.md).  
  
 Následující diagram znázorňuje, jak jsou implementované rozhraní, která podporují řešení a projektu konfigurace:  
  
 ![Obrázek konfigurace rozhraní](../../extensibility/internals/media/vsconfiginterfaces.gif "vsConfigInterfaces")  
Konfigurace rozhraní  
  
 Několik poznámek k předchozímu diagramu:  
  
-   `IDispatch`je označená jako volitelná v objektu konfigurace. Konkrétně je volitelný tak, aby měl rozhraní konfigurace v objektu Procházet.  
  
-   `IVsDebuggableProjectCfg`je označen jako volitelný v objekt konfigurace, ale je nutná pro ladění podpory.  
  
-   `IVsProjectCfg2`je označen jako volitelný v objekt konfigurace, ale je nutný pro výstup seskupování podpory.  
  
-   `Config Provider` Objekt je označen jako objekt volitelné, ale je možnost, kdy k implementaci. Objekt může implementovat na objekt projektu nebo na samostatném objektu.  
  
-   `IVsCfgProvider2`je potřeba pro podporu platformy a úpravu konfigurace. `IVsCfgProvider`Stačí, pokud není implementací této funkce.  
  
-   Některé z těchto objektů na obrázku znázorněné jako samostatné objekty lze spojovat do stejné třídy, kde je to praktické podle požadavků na konkrétní návrh. V dalších tématech v této části ale objekty a rozhraní přidružené k těmto objektům probereme podle scénáře uvedené v diagramu.  
  
-   Některé objekty jsou implementované samostatně. Například projektu a sestavení řešení docházet v samostatných vláknech a objekt, který chcete spravovat život sestavení odděleně od objekt popisující konfigurace pro sestavení.  
  
 Další informace o rozhraní konfigurace objektu a objekt konfigurace poskytovatele rozhraní v předchozím diagramu najdete v tématu [objekt konfigurace projektu](../../extensibility/internals/project-configuration-object.md). Kromě toho [konfigurace projektu pro vytvoření](../../extensibility/internals/project-configuration-for-building.md) poskytuje další informace o rozhraní konfigurace tvůrce a sestavení objektu závislostí a [konfigurace projektu pro správu nasazení](../../extensibility/internals/project-configuration-for-managing-deployment.md) Popisuje další rozhraní připojené ke konfiguraci nástroje pro nasazení a závislostí objekty nasazení. Nakonec [konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md) popisuje výstup skupiny a výstupní objekt rozhraní a použití stránky vlastností k zobrazení a nastavte vlastnosti závislá na konfiguraci.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>   
 [Konfigurace projektu pro vytváření](../../extensibility/internals/project-configuration-for-building.md)   
 [Konfigurace řešení](../../extensibility/internals/solution-configuration.md)