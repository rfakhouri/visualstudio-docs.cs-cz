---
title: "Řešení potíží s VSPackages | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, troubleshooting
- debugging, VSPackages
ms.assetid: 274673e7-72e7-476f-a263-3411b5b874be
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e409d31b4f1e16f735b9b4ef22d42dedccf55a9d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-vspackages"></a>Řešení potíží s VSPackages
Následují nejčastější problémy, které může mít s vaší VSPackage a tipy pro řešení problémů.  
  
### <a name="to-troubleshoot-a-vspackage-that-keeps-visual-studio-from-starting"></a>Chcete-li vyřešit VSPackage, která zajišťuje Visual Studio spustit  
  
-   Spustit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] v nouzovém režimu.  
  
     Spusťte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] v nouzovém režimu, na příkazovém řádku, zadejte **/safemode devenv.exe**.  
  
     Během tohoto procesu jsou načteny žádné VSPackages s výjimkou VSPackages, které jsou součástí s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-load"></a>Chcete-li vyřešit VSPackage nenačte  
  
1.  Ujistěte se, že používáte kořenu registru, ve kterém je zaregistrován VSPackage ke spuštění, obvykle kořenu experimentální registru.  
  
     Další informace najdete v tématu [experimentální instanci](../extensibility/the-experimental-instance.md).  
  
2.  Pokud VSPackage je určeno ke spuštění v kořenu experimentální registru, ujistěte se, zda jsou spuštěny experimentální verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     Chcete-li spustit experimentální verzi, zadejte následující příkaz v příkazovém okně: **devenv /rootsuffix exp**.  
  
3.  Zkontrolujte vaše VSPackage položky registru.  
  
     Další informace najdete v tématu [registrace VSPackages](http://msdn.microsoft.com/en-us/31e6050f-1457-4849-944a-a3c36b76f3dd) a [Správa VSPackages](../extensibility/managing-vspackages.md).  
  
4.  Otevřete **výstup** okno instance [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , nedaří se načíst VSPackage. Informace o proč VSPackage nedaří se načíst nemusí být zobrazeny v okně.  
  
    > [!NOTE]
    >  Pokud spouštíte experimentální verze [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE), zkontrolujte **výstup** okno obě verze.  
  
5.  Zkontrolujte protokol aktivit.  
  
     Další informace najdete v tématu [postupy: použití protokolu činnosti](../extensibility/how-to-use-the-activity-log.md).  
  
6.  Další informace o výjimky vyvolané rozhraní IDE, klikněte na tlačítko **výjimky** na **ladění** nabídky Povolit výjimky. V **výjimky** dialogové okno Vyberte typy výjimek, pro které chcete získat další informace.  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-register"></a>Chcete-li vyřešit VSPackage, který registruje  
  
1.  Ujistěte se, že sestavení VSPackage nachází v důvěryhodném umístění. RegPkg nelze zaregistrovat sestavení v nedůvěryhodných nebo částečně důvěryhodného umístění, například do sdílené síťové složky ve výchozí konfiguraci zabezpečení rozhraní .net. I když se zobrazí upozornění pokaždé, když uživatel vytvoří projekt v nedůvěryhodném umístění, můžete zabránit políčka "příště již tuto zprávu nezobrazovat" Toto upozornění nevyskytla.  
  
### <a name="to-troubleshoot-a-command-that-is-not-visible-or-that-generates-an-error-when-you-click-a-command"></a>Chcete-li vyřešit příkazu, která není viditelná nebo který generuje chybu při klepnutí na příkaz  
  
1.  Pomocí následujícího příkazu na sloučení příkazy nabídky nové nebo se změnily a ty již v prostředí IDE [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku: **/rootsuffix devenv/Setup Exp**.  
  
2.  Ujistěte se, že [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro vaše VSPackage najdete UI.dll.  
  
    1.  Identifikátor CLSID VSPackage naleznete v části balíčky registru:  
  
         HKLM\Software\Microsoft\Visual Studio\\*\<verze >*\Packages  
  
    2.  Zkontrolujte, zda je cesta poskytují podklíč SatelliteDll správné.  
  
### <a name="to-troubleshoot-a-vspackage-that-behaves-unexpectedly"></a>Chcete-li vyřešit VSPackage, který se chová neočekávaně  
  
1.  Nastavte zarážky v kódu.  
  
     Dobré počáteční body pro ladění jsou konstruktoru a inicializační metoda. V oblasti, kterou chcete vyhodnotit, jako je například příkazu nabídky můžete také nastavit zarážky. Pokud chcete povolit zarážky, musíte spustit v ladicím programu.  
  
    1.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
    2.  Na **stránky vlastností** dialogové okno, vyberte **ladění** kartě.  
  
    3.  V **argumenty příkazového řádku** zadejte kořenovou příponu ve vývojovém prostředí, vaše VSPackage cíle. Například pokud chcete vybrat experimentální sestavení, zadejte: **RootSuffix Exp**.  
  
    4.  Na **ladění** nabídky, klikněte na tlačítko **spustit ladění** nebo stiskněte klávesu F5.  
  
        > [!NOTE]
        >  Pokud ladíte projektu, vytvořit nebo načíst existující instanci projektu nyní.  
  
2.  Použijte protokol aktivit.  
  
     Sledování chování VSPackage zápisem informace do protokolu činnosti na klíčové body. Tento postup je obzvláště užitečná při spuštění VSPackage v prostředí s prodejní. Další informace najdete v tématu [postupy: použití protokolu činnosti](../extensibility/how-to-use-the-activity-log.md).  
  
3.  Používejte veřejné symboly.  
  
     Pro zlepšení čitelnosti při ladění, můžete připojit symboly pro ladicí program.  
  
    1.  Z **Nástroje/možnosti** nabídky, přejděte na **ladění nebo symboly** dialogové okno.  
  
    2.  Přidejte tuto **symbolů umístění souboru (.pdb)**:  
  
         [http://msdl.microsoft.com/download/symbols](http://msdl.microsoft.com/download/symbols)  
  
    3.  Chcete-li zvýšit výkon, zadejte složky mezipaměti symbol, například:  
  
        ```  
        C:\symbols  
        ```  
  
### <a name="to-troubleshoot-a-missing-vspackage-or-one-of-its-dependencies"></a>Řešení potíží s chybějící VSPackage nebo jedna z jeho závislostí  
  
1.  Pro spravovaný kód zajistěte, aby byla odkazu cesty správný.  
  
    1.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
    2.  Vyberte **odkazy** ve **stránky vlastností** dialogové okno a ujistěte se, že jsou všechny cesty správný. Alternativně můžete použít **Prohlížeč objektů** k vyhledání odkazované objekty.  
  
         Pro spravovaný kód, můžete použít [Fuslogvw.exe (sestavení vazby Log Viewer)](/dotnet/framework/tools/fuslogvw-exe-assembly-binding-log-viewer) k zobrazení podrobností o načtení sestavení se nezdařilo.  
  
2.  Pro nespravovaného kódu najít identifikátor CLSID VSPackage v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzlu registru CLSID:  
  
     HKLM\Software\Microsoft\Visual Studio\\*\<verze >*\CLSID  
  
 Ujistěte se, že má položka InprocServer32 správnou cestu k souboru VSPackage dll.  
  
## <a name="see-also"></a>Viz také  
 [VSPackages](../extensibility/internals/vspackages.md)