---
title: "Aktualizovat síťovou instalaci sady Visual Studio | Microsoft Docs"
description: "Zjistěte, jak aktualizovat síťovou instalaci sady Visual Studio pomocí příkazu--rozložení"
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 1AF69C0E-0AC9-451B-845D-AE4EDBCEA65C
author: timsneath
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 548ab3168441eeb6366a5bd7f09e52ce4c682e0b
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="update-a-network-based-installation-of-visual-studio"></a>Aktualizace síťovou instalaci sady Visual Studio

Je možné aktualizace rozložení sítě instalace sady Visual Studio pomocí nejnovější aktualizace produktu, tak, aby je bylo možné použila i jako bod instalace pro nejnovější aktualizaci sady Visual Studio a také k údržbě instalace, které jsou již nasazeny do klienta pracovní stanice.

## <a name="how-to-update-a-network-layout"></a>Postup aktualizace síťový diagram
Chcete-li aktualizovat síťové složce instalace, tak, že obsahují nejnovější aktualizace, spusťte příkaz--rozložení přírůstkově stáhnout aktualizované balíčky.

Pokud jste vybrali částečné rozložení při prvním vytvoření rozložení sítě, tato nastavení se uloží.  Všechny příkazy budoucí rozložení pomocí možnosti předchozí plus žádné nové možnosti, které zadáte.  (To je nového v 15.3.)  Pokud používáte rozložení starší verze, používejte stejné parametry příkazového řádku, které jste použili při prvním vytvoření rozložení instalace sítě (jinými slovy, stejné úlohy a jazyky) k aktualizaci jeho obsah.

Pokud hostujete rozložení ve sdílené složce, by měl aktualizovat privátní kopie rozložení (například c:\vs2017offline) a potom po všech aktualizovaný obsah se stáhne, zkopírujte jej do sdílené složky (například \\server\products\VS2017). Pokud to neuděláte, existuje vyšší pravděpodobnost, že všechny uživatele, kteří spustí instalaci v průběhu aktualizace rozložení nemusí být schopné veškerý obsah získat z rozložení, protože není ještě aktualizovala kompletně.

Projděme postup vytvoření a aktualizujte rozložení:

* První tady je příklad vytvoření rozložení zatížením, jeden pro angličtinu pouze:

  ```
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US
  ```

* Chcete-li aktualizovat na novější verzi této stejné rozvržení. Není nutné specifikovat žádné další parametry příkazového řádku. Předchozí nastavení se uložilo a budou používat všechny následné rozložení příkazy v této složce rozložení.  

  ```
  vs_enterprise.exe --layout c:\VS2017Layout  
  ```

* Chcete-li aktualizovat v bezobslužném rozložení na novější verzi. Operaci rozložení spustí proces instalace v nové okno konzoly. Okno je ponechány otevřené, takže uživatelé mohou vidět konečný výsledek a souhrn chyby, ke kterým může dojít. Pokud provádíte operaci rozložení v bezobslužném (například máte skript, který je spuštěn pravidelně aktualizovat na nejnovější verzi vaší rozložení), potom použít `--passive` parametr a tento proces se automaticky zavře okno.

  ```
  vs_enterprise.exe --layout c:\VS2017Layout --passive
  ```

* Chcete-li přidat další zatížení a lokalizovaném jazyce.  (Tento příkaz přidá úloha Azure.)  Plocha spravovaný a Azure jsou nyní zahrnutá v tomto rozložení.  Jazyk prostředky pro angličtinu a češtinu jsou také zahrnuté pro všechny tyto úlohy.  A rozložení se aktualizuje na nejnovější dostupnou verzi.

  ```
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE
  ```

* A nakonec, chcete-li přidat další zatížení a lokalizovaném jazyce bez aktualizace na verzi. (Tento příkaz přidá ASP.NET a webové úlohy.)  Plocha spravovaný, Azure a ASP.NET a webové úlohy jsou nyní zahrnutá v tomto rozložení.  Jazyk prostředky pro angličtinu, němčinu a francouzštinu jsou také zahrnuté pro všechny tyto úlohy.  Rozložení však nebyl aktualizován na nejnovější dostupnou verzi, při spuštění tohoto příkazu.  Zůstane v existující verzi.

  ```
  vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.NetWeb --lang fr-FR --keepLayoutVersion
  ```

## <a name="how-to-deploy-an-update-to-client-machines"></a>Jak nasadit aktualizace do klientských počítačů
V závislosti na tom, jak je nakonfigurované vaše síťové prostředí aktualizace můžete být nasadit pomocí Správce podnikové sítě nebo inicializována z klientský počítač.

* Uživatelé mohou aktualizovat instance Visual Studio, nainstalovaná z offline instalační složku:
  * Spusťte instalační program sady Visual Studio.
  * Potom klikněte na **aktualizace**.

* Správci můžete aktualizovat nasazení klientů sady Visual Studio bez nutnosti zásahu uživatele pomocí dvou samostatných příkazů:
  * Nejdříve aktualizujte instalační program sady Visual Studio: <br>```vs_enterprise.exe --quiet --update```
  * Aktualizujte vlastní aplikace Visual Studio: <br>```vs_enterprise.exe update --installPath "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise" --quiet --wait --norestart```

> [!NOTE]
> Použití [vswhere.exe příkaz](tools-for-managing-visual-studio-instances.md) k identifikaci cestu instalace stávající instanci sady Visual Studio na klientský počítač.

> [!TIP]
> Podrobnosti o tom, jak řídit, kdy oznámení o aktualizaci prezentovány uživatelům najdete v tématu [řízení aktualizace Visual Studio nasazení založené na síti](controlling-updates-to-visual-studio-deployments.md).

## <a name="how-to-verify-a-layout"></a>Postup ověření rozložení
Použití `--verify` k provedení ověření v mezipaměti offline zadaný. Zkontroluje, jestli jsou soubory balíčků chybí nebo je neplatný. Na konci ověření vytiskne seznam chybějících souborů a souborů neplatný.

```
vs_enterprise.exe --layout <layoutDir> --verify
```

Uvnitř layoutDir nelze vyvolat vs_enterprise.exe.


> [!NOTE]
> Některé důležité metadata soubory, které jsou vyžadovány `--verify` možnost musí být v mezipaměti offline rozložení. Pokud tyto soubory metadat chybí, "– Ověřte" nelze spustit, a nabídne instalační program k chybě. Pokud dojde k této chybě, znovu vytvořte nové offline rozložení do jiné složky (nebo do stejné složky, offline mezipaměti. Uděláte to tak, spusťte stejný příkaz rozložení, který jste použili k vytvoření počáteční offline rozložení. Například `Vs_enterprise.exe --layout <layoutDir>`.

Microsoft dodává aktualizace pro Visual Studio pravidelně, tak nové rozložení, který vytvoříte, nemusí být stejnou verzi jako počáteční rozložení.  

## <a name="how-to-fix-a-layout"></a>Jak opravit rozložení
Použití `--fix` k provedení ověření stejné jako `--verify` a také se pokusí opravit zjištěné problémy. `--fix` Proces vyžaduje připojení k Internetu, proto se ujistěte, váš počítač je připojený k Internetu, než můžete vyvolat `--fix`.

```
vs_enterprise.exe --layout <layoutDir> --fix
```

Uvnitř layoutDir nelze vyvolat vs_enterprise.exe.

## <a name="how-to-remove-older-versions-from-a-layout"></a>Postup odebrání starších verzí z rozložení
Po provedení rozložení aktualizace offline mezipaměti, bude složka mezipaměti rozložení může mít některé zastaralé balíčky, které už nejsou potřeba nejnovější instalaci sady Visual Studio. Můžete použít `--clean` možnost odebrat zastaralé balíčky ze složky offline mezipaměti.

K tomu budete potřebovat soubor cesty k manifest(s) katalogu, které obsahují tyto balíčky zastaralé. Můžete najít, že katalogu manifesty ve složce "Archivu" v mezipaměti offline rozložení. Jsou uloženy došlo při aktualizaci rozložení. Ve složce "Archivu" je jeden nebo více "GUID" název složky, z nichž každý obsahuje manifest zastaralé katalogu. Počet složek "GUID" by měl být stejný jako počet aktualizace provedené offline mezipaměti.

Několik soubory jsou uloženy ve složce každý "GUID". Jsou dva soubory týkající se většina soubor "catalog.json" a "version.txt" soubor. Soubor "catalog.json" je zastaralé katalogu manifest je potřeba předat `--clean` možnost. Další version.txt soubor obsahuje verzi tohoto manifestu zastaralé katalogu. Podle toho, číslo verze, můžete rozhodnout, jestli chcete odebrat zastaralé balíčky z tohoto katalogu manifestu. Můžete provést stejný při procházení jiných složkách "GUID". Po provedení rozhodnutí v katalogy chcete vyčistit, spusťte `--clean` příkaz zadáním cesty soubory těchto katalogů.  

Tady je několik příkladů použití--čistou možnost:   

```
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> <file-path-of-catalog2> …
```

```
vs_enterprise.exe --layout <layoutDir> --clean <file-path-of-catalog1> --clean <file-path-of-catalog2> …
```

Můžete také vyvolat vs_enterprise.exe uvnitř &lt;layoutDir&gt;. Tady je příklad:

```  
c:\VS2017Layout\vs_enterprise.exe --layout c:\VS2017Layout --clean c:\VS2017Layout\Archive\1cd70189-fc55-4583-8ad8-a2711e928325\Catalog.json --clean c:\VS2017Layout\Archive\d420889f-6aad-4ba4-99e4-ed7833795a10\Catalog.json
```  

Při spuštění tohoto příkazu analyzuje instalace složky mezipaměti offline najít seznam souborů, které budou odebrány. Pak bude mít možnost zkontrolovat soubory, které se chystáte se odstranit a potvrzení odstranění.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
* [Instalaci sady Visual Studio](install-visual-studio.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Používání parametrů příkazového řádku pro instalaci sady Visual Studio](use-command-line-parameters-to-install-visual-studio.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
* [Ovládací prvek aktualizací pro nasazení založené na síti Visual Studio](controlling-updates-to-visual-studio-deployments.md)
