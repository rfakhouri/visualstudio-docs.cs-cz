---
title: "Odstraňování problémů instalace | Microsoft Docs"
description: "V některých případech může problémů. Pokud instalaci sady Visual Studio nebo upgrade selže, může pomoci tuto stránku."
ms.date: 11/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 556EDD3F-E365-43EE-B3DD-03AA4353F75B
author: timsneath
ms.author: tims
manager: ghogen
ms.openlocfilehash: f0f71dab64a99965facac9ccaa0fff9b53a6e3f6
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="troubleshooting-visual-studio-2017-installation-and-upgrade-issues"></a>Řešení potíží s Visual Studio 2017 instalace a upgrade

## <a name="symptoms"></a>Příznaky
Při pokusu o instalaci nebo aktualizaci Visual Studio 2017, operace se nezdaří.

## <a name="workaround"></a>Alternativní řešení
Chcete-li tento problém obejít, postupujte podle těchto kroků.

### <a name="step-1---check-whether-this-problem-is-a-known-issue"></a>Krok 1 – Zkontrolujte, jestli tento problém se o známý problém
Existují některé známé problémy s Visual Studio Instalační program, který společnost Microsoft pracuje na řešení. Pokud chcete zobrazit, pokud je alternativní řešení pro váš problém, zkontrolujte [části Známé problémy naše poznámky k verzi](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#known-issues).

### <a name="step-2---check-with-the-developer-community"></a>Krok 2 – Kontrola s komunitou vývojářů
Vyhledávání na vaše chybová zpráva s [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/spaces/8/index.html). Ostatní členové komunity služby může mít popsané řešení svých problémů.

### <a name="step-3---delete-the-visual-studio-installer-directory-to-fix-upgrade-problems"></a>Krok 3 – odstranit adresář instalační program Visual Studio k řešení problémů s upgradem
Instalační program Visual Studio zavaděč je minimální spustitelný soubor šedé –, který nainstaluje zbytek instalační program Visual Studio. Odstraňování souborů Instalační program Visual Studio a pak znovu spustit zavaděč může vyřešit chyby některé aktualizace.

**Poznámka:** provedením následujících akcí přeinstaluje soubory Instalační program Visual Studio a resetuje metadata instalace.

1. Ukončete instalační program sady Visual Studio.
2. Odstraňte adresář instalační program Visual Studio. Adresář je obvykle `C:\Program Files (x86)\Microsoft Visual Studio\Installer`.
3. Spusťte instalační program Visual Studio zaváděcího nástroje. Možná zavaděč v složky se staženými soubory s názvem souboru, který následuje `vs_[Visual Studio edition]__*.exe` vzor. Pokud nenajdete tuto aplikaci, si můžete stáhnout zavaděč přechodem na [Visual Studio stáhne](https://www.visualstudio.com/downloads/) stránky a kliknutím na **Stáhnout** vaší verze sady Visual Studio. Spuštění spustitelného souboru resetovat metadata instalace.
4. Zkuste instalaci nebo aktualizaci sady Visual Studio znovu. Pokud instalační program dále nedaří, přejděte k dalšímu kroku.

### <a name="step-4---report-a-problem"></a>Krok 4 – nahlásit problém
V některých situacích, například související s poškozené soubory může mít problémy se pro ně v případ od případu:

1. Shromážděte vaše protokoly instalace. V tématu [jak získat protokoly instalace sady Visual Studio](#how-to-get-the-visual-studio-installation-logs) podrobnosti.
2. Spusťte instalační program Visual Studio a potom klikněte na **nahlásit problém** otevřete nástroj Visual Studio zpětnou vazbu.
![Můžete klikněte na tlačítko poskytnout zpětnou vazbu, chcete-li spustit nástroj zpětné vazby](media/report-a-problem.png)
3. Zadejte název sestavy problém a poskytnout příslušné podrobnosti. Klikněte na tlačítko **Další** přejít na **přílohy** části a pak připojte soubor generovaný protokolu (obvykle je soubor v `%TEMP%\vslogs.zip`).
4. Klikněte na tlačítko **Další** zkontrolujte zprávy o potížích a potom klikněte na **odeslání**.

### <a name="step-5---run-installcleanupexe-to-remove-installation-files"></a>Krok 5 – spustit InstallCleanup.exe odebrat instalační soubory
Jako poslední možnost, můžete [odebrat Visual Studio](remove-visual-studio.md) odebrat všechny instalační soubory a informace o produktu.

1. Postupujte podle pokynů v [odebrat Visual Studio](remove-visual-studio.md).
2. Znovu spustit zavaděč, který je popsán v [krok 3 – odstranit adresář instalační program Visual Studio k řešení problémů s upgradem](#step-3--delete-the-visual-studio-installer-directory-to-fix-upgrade-problems).
3. Zkuste instalaci nebo aktualizaci sady Visual Studio znovu.

### <a name="step-6---contact-us-optional"></a>Krok 6 – kontaktujte nás (volitelné)
Pokud žádné další kroky umožňují úspěšně nainstalovat, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

## <a name="how-to-troubleshoot-an-offline-installer"></a>Řešení potíží s offline instalačního programu
Tady je tabulku známé problémy a některé řešení při instalaci z místní rozložení, které můžou pomoct.

| Problém       | Položka                   | Řešení |
| ----------- | ---------------------- | -------- |
| Uživatelé nebudou mít přístup k souborům. | oprávnění (ACL) | Zajistěte, aby upravit oprávnění (ACL), tak, aby se ostatním uživatelům udělit přístup pro čtení *před* sdílet offline instalace. |
| Nové úlohy, komponenty nebo jazyky nepodaří nainstalovat.  | `--layout`  | Ujistěte se, zda máte přístup k Internetu, pokud instalovat z částečné rozložení a vyberete zatížení, komponenty nebo jazyky, které nebyly staženy dříve v tomto částečné rozložení. |

## <a name="how-to-get-the-visual-studio-installation-logs"></a>Jak získat protokoly instalace sady Visual Studio
Instalační protokoly jsou potřeba k odstranění většiny potíží instalace. Když odešlete problém pomocí [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) v instalačním programu Visual Studio tyto protokoly jsou automaticky obsažené v sestavě.

Pokud kontaktujete Microsoft Support, budete možná muset zadat tyto protokoly instalace pomocí [Microsoft Visual Studio a rozhraní .NET Framework protokolu kolekce nástroj](https://aka.ms/vscollect). Nástroj protokol kolekce shromažďuje protokoly instalace z všechny součásti nainstalovány 2017 Visual Studio, včetně rozhraní .NET Framework, sady Windows SDK a SQL Server. Shromažďuje taky informace o počítači, instalační služba systému Windows inventář a informace v protokolu událostí systému Windows pro instalační program Visual Studio, instalační služba systému Windows a nástroj Obnovení systému.

Shromažďovat protokoly:

1. [Stáhněte si nástroj](https://aka.ms/vscollect).
2. Otevřete příkazový řádek pro správu.
3. Spustit `Collect.exe` z adresáře, kam jste uložili nástroj.
4. Najít výsledná `vslogs.zip` ve vaší `%TEMP%` adresáři, například `C:\Users\YourName\AppData\Local\Temp\vslogs.zip`.

> [!NOTE]
> Nástroj musí být spuštěn pod stejný uživatelský účet, který byl běh neúspěšnou instalaci. Pokud používáte nástroj z jiného uživatelského účtu, nastavte `–user:<name>` možnost zadat uživatelský účet, pod kterým byla spouštěna neúspěšnou instalaci. Spustit `Collect.exe -?` z příkazového řádku správce pro další informace o možnosti a využití.

## <a name="more-support-options"></a>Další možnosti podpory

Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.

Tady je několik více možností:

* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (To vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
* [Příručka administrátora sady Visual Studio](visual-studio-administrator-guide.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
* [Odebrat Visual Studio 2017](remove-visual-studio.md)
