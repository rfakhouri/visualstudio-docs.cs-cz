---
title: Konfigurace pro sestavení projektu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], configuration for building
- project configurations, building
ms.assetid: 2c83615d-fa4d-4b9f-b315-7a69b3000da0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fd9464105d777c0d488175ad67e1481022caa2d1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66328542"
---
# <a name="project-configuration-for-building"></a>Konfigurace projektu pro sestavení
Seznam konfigurací řešení pro dané řešení se spravuje přes dialogové okno konfigurace řešení.

 Uživatel může vytvořit konfigurace další řešení, každý s vlastním jedinečným názvem. Když uživatel vytvoří nová konfigurace řešení, rozhraní IDE použije výchozí k názvu odpovídající konfigurace v projektech nebo ladění, pokud neexistuje žádný odpovídající název. Uživatel může změnit výběr podle specifických požadavků v případě potřeby. Jedinou výjimkou z tohoto chování je, když projekt podporuje konfigurace, která odpovídá názvu nová konfigurace řešení. Předpokládejme například, že řešení obsahuje Project1 a "project2". Project1 má konfigurace projektu, ladění, maloobchodní prodej a MyConfig1. "Project2" má konfigurace projektu, ladění, maloobchodní prodej a MyConfig2.

 Pokud uživatel vytvoří nová konfigurace řešení s názvem MyConfig2, Project1 sváže jeho konfiguraci ladění konfigurace řešení ve výchozím nastavení. "Project2" také vytvoří vazbu jeho konfigurace MyConfig2 konfigurace řešení ve výchozím nastavení.

> [!NOTE]
> Vazba je velká a malá písmena.

 Když uživatel vybere **vícenásobný výběr** položek v rozevíracím seznamu konfigurace prostředí se zobrazí dialogové okno, které poskytuje seznam dostupných konfigurací.

 ![Více konfigurací](../../extensibility/internals/media/vsmultiplecfgs.gif "vsMultipleCfgs") více konfigurací

 V tomto dialogovém okně může uživatel vybrat jednu nebo více konfigurací. Po výběru odrážejí hodnoty vlastností zobrazí v dialogovém okně stránky vlastností průnik hodnot pro zvolené konfigurace.

 Zobrazit [konfigurace řešení](../../extensibility/internals/solution-configuration.md) informace týkající se přidání a přejmenování konfigurace pro projekty a řešení.

 Závislosti projektu a pořadí sestavení jsou nezávislá konfigurace řešení: to znamená, které můžete nastavit jenom jednu závislost strom pro všechny projekty v řešení. Pravým tlačítkem myši na projekt nebo řešení a vyberete buď **závislosti projektu** nebo **pořadí sestavení projektu** možnost otevře **závislosti projektu** dialogové okno. Můžete otevřít také z **projektu** nabídky.

 ![Závislosti projektu](../../extensibility/internals/media/vsprojdependencies.gif "vsProjDependencies") závislosti projektu

 Závislosti projektu určení pořadí, ve kterém sestavení projektů. Na kartě pořadí sestavení v dialogovém okně můžete zobrazit přesný pořadí, ve kterém se projekty v rámci řešení sestavení a chcete-li změnit pořadí sestavení, použijte kartu závislosti.

> [!NOTE]
> Projekty v seznamu, které jejich zaškrtnutých políček, ale zobrazují šedě, se přidaly prostředí z důvodu explicitní závislosti, které jsou určené <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> rozhraní a nedá se změnit. Například přidáním odkazu na projekt z [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu do jiného projektu automaticky přidá závislost sestavení, který lze odebrat pouze tak, že odstraníte odkaz. Projekty, jejichž zaškrtávací políčka jasné a zobrazují šedě, nelze vybrat, protože to by vytvořilo smyčku závislosti (například Project1 by být závislá na "project2" a "project2" by být závislá na Project1), který by manipulace blokováním do sestavení.

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] procesy sestavení zahrnují typické kompilace a operace odkazů, které jsou vyvolány pomocí jediného příkazu sestavení. Dva procesy sestavení může také podporovat: spuštění operace vyčištění odstranit všechny výstupní položky od předchozího sestavení a kontrolu aktuálnosti k určení, jestli se změnila výstupní položky v konfiguraci.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> objekt vrací odpovídající <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> (vrácená <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>) ke správě jejich procesy sestavení. Zaznamenat stav z operace sestavení probíhající, se provedené konfigurace volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildStatusCallback>, rozhraní implementované prostředí a druhý objekt zajímá událostí stavu sestavení.

 Jakmile sestavená, nastavení konfigurace slouží k určení, zda lze spustit pod kontrolu ladicího programu. Konfigurace implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg> v zájmu podpory ladění.

 Po implementaci závislosti projektu, můžete programově manipulovat s závislosti pomocí modelu automatizace. Volání <xref:EnvDTE.SolutionBuild.BuildDependencies%2A> v modelu automatizace. Neexistují žádné dostupné rozhraní VSIP úrovni rozhraní API, které umožňují přímé manipulace Správce konfigurace sestavení řešení a jejich vlastnosti.

 Kromě toho můžete zadat do mřížky v okně závislosti projektu. Další informace najdete v tématu [zobrazení mřížky okna vlastnosti](../../extensibility/internals/properties-display-grid.md).

## <a name="see-also"></a>Viz také
- [Správa možností konfigurace](../../extensibility/internals/managing-configuration-options.md)
- [Konfigurace projektu pro správu nasazení](../../extensibility/internals/project-configuration-for-managing-deployment.md)
- [Konfigurace projektu pro výstup](../../extensibility/internals/project-configuration-for-output.md)