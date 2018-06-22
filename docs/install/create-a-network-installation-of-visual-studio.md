---
title: Vytvoření síťové instalace sady Visual Studio
description: Naučte se vytvářet umístění síťové instalace pro nasazení sady Visual Studio v rámci organizace.
ms.date: 10/17/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 4CABFD20-962E-482C-8A76-E4012052F701
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f25e277a4743d27115485e791fd44f12078a4b2f
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282584"
---
# <a name="create-a-network-installation-of-visual-studio-2017"></a>Vytvořit sítě instalaci sady Visual Studio 2017

Správce podnikové sítě běžně, vytvoří bod instalace sítě pro nasazení do klientských pracovních stanic. Jsme jste chtěli Visual Studio 2017 umožnit pro ukládání do mezipaměti soubory pro počáteční instalaci společně s všechny aktualizace produktu do jediné složky. (Tento proces se také označuje jako _vytváření rozložení_.) Jsme k tomu, aby klientské pracovní stanice pomocí stejné umístění v síti můžete spravovat jejich instalace i v případě, že ještě neprovedli aktualizaci na nejnovější servisní aktualizace.

 > [!NOTE]
 > Pokud máte víc edicí sady Visual Studio používán v rámci vaší organizace (například jak Visual Studio Professional a Visual Studio Enterprise), musíte vytvořit sdílenou složku instalace samostatnou síť pro každé edici.

## <a name="download-the-visual-studio-bootstrapper"></a>Stáhněte si Visual Studio zaváděcího nástroje

**Stáhněte si** edice sady Visual Studio, které chcete. Ujistěte se, klikněte na **Uložit**a potom klikněte na **otevřít složku**.

Vaše instalačního programu&mdash;nebo být konkrétnější, soubor zaváděcího nástroje&mdash;by měl shodovat s jedním z následujících akcí.

|Edice | Stáhnout|
|-------------|-----------------------|
|Visual Studio Enterprise | [**vs_enterprise.exe**](https://aka.ms/vs/15/release/vs_enterprise.exe) |
|Visual Studio Professional | [**vs_professional.exe**](https://aka.ms/vs/15/release/vs_professional.exe) |
|Visual Studio Community | [**vs_community.exe**](https://aka.ms/vs/15/release/vs_community.exe) |

Zahrnout další podporované samozaváděcích [vs_buildtools.exe](https://aka.ms/vs/15/release/vs_buildtools.exe), [vs_feedbackclient.exe](https://aka.ms/vs/15/release/vs_feedbackclient.exe), [vs_teamexplorer.exe](https://aka.ms/vs/15/release/vs_teamexplorer.exe), [vs_testagent.exe](https://aka.ms/vs/15/release/vs_testagent.exe), [vs_testcontroller.exe](https://aka.ms/vs/15/release/vs_testcontroller.exe), a [vs_testprofessional.exe](https://aka.ms/vs/15/release/vs_testprofessional.exe).

## <a name="create-an-offline-installation-folder"></a>Vytvoření offline instalační složku.

Musí mít připojení k Internetu k dokončení tohoto kroku. Vytvoření offline instalace s všechny jazyky a všechny funkce, použijte jednu z následujících příkladech příkazů.

   > [!IMPORTANT]
   > Dokončení rozložení Visual Studio 2017 vyžaduje alespoň 35 GB místa na disku a může trvat nějakou dobu ke stažení.  Najdete v článku [přizpůsobení síťový diagram](#customizing-the-network-layout) část Podrobnosti o tom, jak vytvořit rozložení s pouze komponenty chcete nainstalovat.
   >
   > [!TIP]
   > Ujistěte se, spusťte příkaz z adresáře ke stažení. Obvykle to je `C:\Users\<username>\Downloads` v počítači se systémem Windows 10.

- Visual Studio Enterprise spusťte příkaz:

  ```vs_enterprise.exe --layout c:\vs2017offline```

- Visual Studio Professional spusťte příkaz:

  ```vs_professional.exe --layout c:\vs2017offline```

- Visual Studio Community spusťte příkaz:

  ```vs_community.exe --layout c:\vs2017offline```

## <a name="modify-the-responsejson-file"></a>Upravte soubor response.json

Můžete upravit response.json nastavit výchozí hodnoty, které se používají, když se spustí instalační program.  Například můžete nakonfigurovat `response.json` soubor a vyberte konkrétní sadu úloh, vybere se automaticky.
V tématu [automatizovat instalaci sady Visual Studio se souborem odpovědí](automated-installation-with-response-file.md) podrobnosti.

## <a name="copy-the-layout-to-a-network-share"></a>Zkopírujte rozložení do sdílené síťové složky

Rozložení ve sdílené síťové složce hostitele, takže ho můžete spustit z jiných počítačů.
* Příklad:<br>
```xcopy /e c:\vs2017offline \\server\products\VS2017```

## <a name="customizing-the-network-layout"></a>Přizpůsobení rozložení sítě

Existuje několik možností, které můžete použít k přizpůsobení síťový diagram. Můžete vytvořit částečné rozložení, který obsahuje pouze konkrétní sadu [národní prostředí](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales), [úlohy, komponent a jejich doporučená nebo volitelné závislosti](workload-and-component-ids.md). To může být užitečné, pokud víte, že se chystáte nasadit jenom podmnožinu úlohy na klientských pracovních stanic. Typické parametry příkazového řádku pro přizpůsobení rozložení patří:

* ```--add``` Chcete-li určit [ID úlohy nebo součást](workload-and-component-ids.md).  Pokud `--add` se používá pouze úlohy a součásti zadaným `--add` staženy.  Pokud `--add` se nepoužívá, všechny úlohy a součásti staženy.
* ```--includeRecommended``` Zahrnout všechny součásti, které jsou doporučené pro zadané ID úlohy
* ```--includeOptional``` Zahrnout všechny doporučené a volitelné součásti pro zadané ID pracovní vytížení.
* ```--lang``` Chcete-li určit [národní prostředí](use-command-line-parameters-to-install-visual-studio.md#list-of-language-locales).

Tady je několik příkladů o tom, jak vytvořit vlastní částečné rozložení.

* Chcete-li stáhnout všechny úlohy a součásti pro pouze jeden jazyk, spusťte: <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US```
* Chcete-li stáhnout všechny úlohy a součásti pro více jazyky, spusťte: <br>```vs_enterprise.exe --layout C:\vs2017offline --lang en-US de-DE ja-JP```
* Chcete-li stáhnout jeden úloh pro všechny jazyky, spusťte <br> ```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --includeRecommended```
* Chcete-li stáhnout dvě úlohy a jeden volitelné součásti pro tři jazyky, spusťte: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended --lang en-US de-DE ja-JP ```
* Chcete-li stáhnout dvě úlohy a všechny jejich doporučené součásti, spusťte: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeRecommended ```
* Chcete-li stáhnout dvě úlohy a všechny jejich doporučené a volitelné součásti, spusťte: <br>```vs_enterprise.exe --layout C:\vs2017offline --add Microsoft.VisualStudio.Workload.Azure --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Component.GitHub.VisualStudio --includeOptional ```

### <a name="new-in-153"></a>Novinka v 15.3

Když spustíte příkaz rozložení, možnosti, které zadáte ukládají (například úlohy a jazyky). Rozložení následné příkazy bude obsahovat všechny předchozí možnosti.  Tady je příklad rozložení jeden zatížení pro angličtinu pouze:

```vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --lang en-US```

Pokud chcete aktualizovat na novější verzi této rozložení, není nutné specifikovat žádné další parametry příkazového řádku. Předchozí nastavení jsou uloženy a používané všechny následné rozložení příkazy v této složce rozložení.  Příkaz aktualizuje existující částečné rozložení.

```vs_enterprise.exe --layout c:\VS2017Layout```

Pokud chcete přidat další zatížení, zde je příklad toho, jak to udělat. V takovém případě přidáme úloha Azure a v lokalizovaném jazyce.  Nyní plocha spravovaný a Azure jsou zahrnuty v tomto rozložení.  Jazyk prostředky pro angličtinu a češtinu jsou zahrnují pro všechny tyto úlohy. Rozložení se aktualizuje na nejnovější dostupnou verzi.

```vs_enterprise.exe --layout c:\VS2017Layout --add Microsoft.VisualStudio.Workload.Azure --lang de-DE```

Pokud chcete aktualizovat existující rozložení na úplné rozložení, použijte--všechny možnosti, jak je znázorněno v následujícím příkladu.

```vs_enterprise.exe --layout c:\VS2017Layout --all```

## <a name="deploying-from-a-network-installation"></a>Nasazení z instalace sítě

Správci můžou nasadit sady Visual Studio na klientské pracovní stanice v rámci instalační skript. Nebo, uživatelé, kteří mají práva správce můžete spustit instalační program přímo ze sdílené složky pro instalaci sady Visual Studio na jejich počítače.

- Uživatele můžete nainstalovat spuštěním: <br>```\\server\products\VS2017\vs_enterprise.exe```
- Správce můžete nainstalovat v bezobslužném režimu spuštěním: <br>```\\server\products\VS2017\vs_enterprise.exe --quiet --wait --norestart```

> [!TIP]
> Při spuštění v rámci dávkového souboru `--wait` možnost zajistí, že `vs_enterprise.exe` proces čeká na dokončení instalace je před vrátí ukončovací kód. To je užitečné, pokud chce správce podnikové sítě provádět další akce instalace byla dokončena. (například k [použít kód product key pro úspěšnou instalaci](automatically-apply-product-keys-when-deploying-visual-studio.md)) ale musí počkat na dokončení zpracování instalace Návratový kód z této instalace.  Pokud nepoužijete `--wait`, `vs_enterprise.exe` proces ukončen před instalace je dokončena a vrátí nesprávné ukončovací kód, který nepředstavuje stavu operace instalace.

Při instalaci z rozložení obsahu, který je nainstalován se získávají z rozložení. Nicméně pokud vyberete komponenty, která není v rozložení, ho bude možné získat z Internetu.  Pokud chcete zabránit instalaci sady Visual Studio stáhnout veškerý obsah, který nebyl nalezen v rozložení, použijte `--noWeb` možnost.  Pokud `--noWeb` se používá a rozložení chybí veškerý obsah, který je vybrán nainstalují, instalace selže.

### <a name="error-codes"></a>Kódy chyb

Pokud jste použili `--wait` parametr a potom v závislosti na výsledku operace, `%ERRORLEVEL%` proměnná prostředí je nastavená na jednu z následujících hodnot:

  | **Hodnota** | **výsledek** |
  | --------- | ---------- |
  | 0 | Operace byla úspěšně dokončena |
  | 3010 | Operace úspěšně dokončena, ale instalace vyžaduje restart, před použitím |
  | Ostatní | Došlo k selhání podmínku – Zkontrolujte protokoly pro další informace |

## <a name="updating-a-network-install-layout"></a>Aktualizuje se síťové instalace rozložení

Jakmile budou k dispozici aktualizace produktu, můžete chtít [aktualizovat síťový diagram instalace](update-a-network-installation-of-visual-studio.md) začlenit aktualizované balíčky.

## <a name="how-to-create-a-layout-for-a-previous-visual-studio-2017-release"></a>Postup vytvoření rozložení pro předchozí verze Visual Studio 2017

> [!NOTE]
> Visual Studio 2017 samozaváděcích, které jsou dostupné na [VisualStudio.com](http://visualstudio.microsoft.com) stáhněte a nainstalujte nejnovější verzi Visual Studio 2017, která je k dispozici vždy, když běží. Pokud ještě dnes stáhnout zaváděcího nástroje Visual Studio a spustit od tohoto okamžiku šest měsíců, nainstaluje na Visual Studio 2017 vydání, které je k dispozici v tomto později. Pokud vytvoříte rozložení, instalace sady Visual Studio z tohoto rozložení nainstaluje určitou verzi sady Visual Studio, která existuje v rozložení. I v případě, že na novější verzi může být online, abyste měli k verzi sady Visual Studio, který je v rozložení.

Pokud potřebujete vytvořit rozložení pro starší verze Visual Studio 2017, můžete přejít na https://my.visualstudio.com ke stažení "pevné" verzích samozaváděcích Visual Studio 2017.

### <a name="how-to-get-support-for-your-offline-installer"></a>Jak získat podporu pro vaše offline instalačního programu

Pokud dojde k potížím s offline instalace, chceme vědět o něm. Nejlepší způsob, jak Řekněte nám, je pomocí [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj. Použijete-li tento nástroj, můžete nám odeslat telemetrie a protokoly musíme Pomozte nám diagnostikovat a opravit potíže.

Další možnosti podpory k dispozici, máme příliš. Seznam najdete v tématu naše [kontaktujte nás](../ide/how-to-report-a-problem-with-visual-studio-2017.md) stránky.

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Příručka správce Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio s použitím parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
* [ID úloh a komponent sady Visual Studio](workload-and-component-ids.md)
