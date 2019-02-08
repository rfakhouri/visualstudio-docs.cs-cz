---
title: Řešení problémů s poškozenými odkazy
ms.date: 03/21/2017
ms.topic: troubleshooting
helpviewer_keywords:
- C# projects, references
- Visual Basic projects, references
- troubleshooting references
- referencing files from projects
- referencing components, troubleshooting
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f9095e3b8c1f80b35b2d135c122c2d7230c1f8c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55954748"
---
# <a name="troubleshoot-broken-references"></a>Řešení problémů s poškozenými odkazy

Pokud vaše aplikace se pokusí použít poškozený odkaz, je vygenerována chyba výjimky. Nebylo možné najít odkazovaná součást je primární aktivační událost pro chybu, ale existuje několik situací ve kterých lze považovat za odkazem nefunkční. Tyto instance jsou uvedeny v následujícím seznamu:

- Cesta odkazu projekt je nesprávné nebo neúplné.

- Odkazovaný soubor se odstranil.

- Odkazovaný soubor byl přejmenován.

- Připojení k síti nebo ověřování se nezdařilo.

- Odkazuje na komponentu modelu COM, který není nainstalován v počítači.

Toto jsou řešení těchto problémů.

> [!NOTE]
> Soubory v sestavení je odkazováno pomocí absolutní cesty v souboru projektu. Proto je možné pro uživatele, kteří pracují v prostředí vývoj chybí odkazovaná sestavení svého místního prostředí. Aby nedocházelo k těmto chybám, je lepší v těchto případech pro přidání odkazů typu projekt projekt. Další informace najdete v tématu [programování se sestaveními](/dotnet/framework/app-domains/programming-with-assemblies).

## <a name="reference-path-is-incorrect"></a>Cesta odkazu je nesprávný

Pokud projekty jsou sdíleny v různých počítačích, nemusí při komponenty se nachází v jiném adresáři na každém počítači nalezeny některé odkazy. Odkazy jsou uloženy pod názvem souboru součásti (například *MyComponent*). Při přidání odkazu do projektu, umístění složky souboru součásti (například *C:\MyComponents*) se připojí **ReferencePath** vlastnosti projektu.

Při otevření projektu, pokusy o vyhledání těchto souborů odkazovaná součást vyhledáváním v adresářích na zadané cestě odkazu. Pokud je projekt otevřen v počítači, který ukládá komponenty v jiném adresáři, jako například *D:\MyComponents*, se nenašel odkaz a objeví se chyba v **seznamu úkolů**.

Chcete-li vyřešit tento problém, můžete odstranit poškozený odkaz a nahradili ho pomocí **přidat odkaz** dialogové okno. Druhým řešením je použít **cestu odkazu** položek na stránkách vlastností projektu a upravit složky v seznamu tak, aby odkazovala na správné umístění. **Cestu odkazu** trvale uloženou vlastnost pro každého uživatele na každém počítači. Změna cesty k odkazu proto neovlivňuje ostatní uživatelé z projektu.

> [!TIP]
> Odkazy typu projekt projekt není nutné tyto problémy. Z tohoto důvodu je použijte místo odkazy na soubory, pokud je to možné.

### <a name="to-fix-a-broken-project-reference-by-correcting-the-reference-path"></a>Chcete-li vyřešit poškozený odkaz projektu tím, že opraví cesta odkazu

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a klikněte na tlačítko **vlastnosti**.

   **Návrháře projektu** se zobrazí.

1. Pokud používáte Visual Basic, vyberte **odkazy** stránky a klikněte na tlačítko **cesty odkazů** tlačítko. V **cesty odkazů** dialogového okna zadejte cestu ke složce, která obsahuje položku, kterou chcete odkazovat **složky** pole a potom klikněte na **přidat složku** tlačítko.

    Pokud používáte C#, vyberte **cesty odkazů** stránky. V **složky** pole, zadejte cestu ke složce, která obsahuje položku, kterou chcete odkazovat a klikněte **přidat složku** tlačítko.

## <a name="referenced-file-has-been-deleted"></a>Odkazovaný soubor byl odstraněn.

Je možné, že odkazovaný soubor je odstraněný a už neexistuje na disku.

### <a name="to-fix-a-broken-project-reference-for-a-file-that-no-longer-exists-on-your-drive"></a>Chcete-li vyřešit porušení projektu odkaz pro soubor, který již existuje na disku

- Odstraňte odkaz.

- Pokud existuje odkaz na jiné místo v počítači, přečtěte si je z tohoto umístění.

## <a name="referenced-file-has-been-renamed"></a>Odkazovaný soubor byl přejmenován.

Je možné, že byl přejmenován soubor, který se odkazuje.

### <a name="to-fix-a-broken-reference-for-a-file-that-has-been-renamed"></a>Chcete-li vyřešit poškozený odkaz pro soubor, který se přejmenoval

- Odstranit odkazy a pak přidejte odkaz na soubor přejmenován.

- Pokud existuje odkaz na jiné místo v počítači, je nutné jej načíst z tohoto umístění.

## <a name="network-connection-or-authentication-has-failed"></a>Připojení k síti nebo ověřování se nezdařilo

Může být mnoho možných příčin nepřístupných souborů: došlo k chybě síťového připojení nebo se nezdařilo ověřování, například. Každou příčinou může být jedinečný prostředek obnovení; například budete muset obrátit na místního správce pro přístup k potřebným prostředkům. Odstranění odkazu a oprava kódu, který používá ho ale vždy možnost.

## <a name="com-component-is-not-installed-on-computer"></a>Na počítači není nainstalovaná komponenta modelu COM

Pokud uživatel byl přidán odkaz na komponentu COM a druhý uživatel pokusí o spuštění kódu na počítači, který nemá tuto součást nainstalovaná, druhý uživatel dojde k chybě, že je odkaz poškozený. Instalace součásti na druhý počítač bude opravte chybu. Další informace o tom, jak pomocí odkazů na komponenty modelu COM ve vašich projektech najdete v tématu [interoperabilita modelů COM v aplikacích .NET Framework](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications).

## <a name="see-also"></a>Viz také:

- [Stránka Odkazy, Návrhář projektu (Visual Basic)](../ide/reference/references-page-project-designer-visual-basic.md)