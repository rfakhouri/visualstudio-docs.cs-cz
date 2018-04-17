---
title: Řešení potíží s poškozenými odkazy | Microsoft Docs
ms.custom: ''
ms.date: 03/21/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- C# projects, references
- Visual Basic projects, references
- troubleshooting references
- referencing files from projects
- referencing components, troubleshooting
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 256e7018b29402a2d67693de3c8e2cfe18ea2f71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-broken-references"></a>Řešení potíží s poškozenými odkazy

Pokud vaše aplikace se pokusí použít poškozený odkaz, je generována chyba výjimky. Neschopnost najít odkazovanou komponentu je primární aktivační událost chyby, ale existuje několik situací ve kterých lze považovat za odkaz poškozený. Tyto instance jsou uvedeny v následujícím seznamu:

- Cesta odkazu projektu je nesprávná nebo neúplná.

- Odkazovaný soubor byl odstraněn.

- Odkazovaný soubor byl přejmenován.

- Síťové připojení nebo ověřování se nezdařilo.

- Odkazuje na komponentu modelu COM, který není nainstalován v počítači.

Níže jsou uvedeny náhrad těchto problémů.

> [!NOTE]
> Soubory v sestavení jsou odkazovány pomocí absolutní cesty v souboru projektu. Proto je možné pro uživatele, kteří pracují v multi vývojovém prostředí chybí odkazované sestavení ve svém místním prostředí. Aby se zabránilo tyto chyby, je lepší v těchto případech přidat odkazy na projekt na projekt. Další informace najdete v tématu [programování se sestaveními](/dotnet/framework/app-domains/programming-with-assemblies).

## <a name="reference-path-is-incorrect"></a>Cesta odkazu je nesprávný

Pokud projekty jsou sdíleny na různých počítačích, nemusí při součást se nachází v jiném adresáři v každém počítači nalezena některé odkazy. Odkazy jsou uloženy pod názvem souboru součásti (například MyComponent). Když je přidán odkaz na projekt, umístění složky souboru komponenty (například C:\MyComponents\\) se připojí k **ReferencePath** projektu vlastnost.

Při otevření projektu, pokusí se vyhledat tyto soubory odkazované komponenty podle adresáře v cestě odkazu. Pokud je na počítači, který ukládá součásti v jiném adresáři, jako je například D:\MyComponents otevřít projekt\\, odkaz nelze nalézt a chyba se zobrazí v seznamu úloh.

Chcete-li tento problém vyřešit, můžete odstranit poškozený odkaz a pak jej nahradit pomocí dialogového okna Přidat odkaz. Jiným řešením je použití **referenční cesty pro** položky na stránkách vlastností projektu a upravit složky v seznamu tak, aby odkazovaly do správných umístění. **Referenční cesty pro** vlastnost je uložena pro každého uživatele na každém počítači. Změna cesty k odkazu proto neovlivňuje ostatní uživatelé projektu.

> [!TIP]
> Odkazy na projekt na projekt nemají tyto problémy. Z tohoto důvodu je použijte místo odkazů na soubor, pokud je to možné.

### <a name="to-fix-a-broken-project-reference-by-correcting-the-reference-path"></a>Opravte cestu odkazu opravit poškozený odkaz projektu

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a klikněte na **vlastnosti**.

   **Návrhář projektu** se zobrazí.

1. Pokud používáte Visual Basic, vyberte **odkazy** a klikněte na tlačítko **cesty odkazů** tlačítko. V **cesty odkazů** dialogovém okně zadejte cestu ke složce obsahující položku, kterou chcete odkazovat v **složky** pole a pak klikněte na **přidat složku** tlačítko.

    Pokud používáte C#, vyberte **cesty odkazů** stránky. V **složky** pole, zadejte cestu ke složce obsahující položku, kterou chcete odkazovat, a pak klikněte na **přidat složku** tlačítko.

## <a name="referenced-file-has-been-deleted"></a>Odkazovaný soubor byl odstraněn

Je možné, že odkazovaný soubor byl odstraněn a už existuje na disku.

### <a name="to-fix-a-broken-project-reference-for-a-file-that-no-longer-exists-on-your-drive"></a>Chcete-li odstranit poškozený odkaz projektu pro soubor, který už existuje na disku

- Odstraňte odkaz.

- Pokud odkaz existuje v jiném umístění v počítači, přečtěte si ho z tohoto umístění.

## <a name="referenced-file-has-been-renamed"></a>Odkazovaný soubor byl přejmenován.

Je možné, že odkazovaný soubor byl přejmenován.

### <a name="to-fix-a-broken-reference-for-a-file-that-has-been-renamed"></a>Chcete-li odstranit poškozený odkaz pro soubor, který byl přejmenován

- Odstraňte odkaz na a pak přidejte odkaz na základě přejmenovaného souboru.

- Pokud odkaz existuje v jiném umístění v počítači, musíte jej načíst z tohoto umístění.

## <a name="network-connection-or-authentication-has-failed"></a>Síťové připojení nebo ověřování se nezdařilo

Může být možné příčiny nepřístupných souborů: došlo k chybě síťového připojení nebo neúspěšné ověřování, například. Každou příčinou může být jedinečný prostředek obnovení; Například můžete chtít obraťte se na místního správce pro přístup k požadované prostředky. Odstranění odkazu a oprava kódu, který ho používají je však vždy možnost.

## <a name="com-component-is-not-installed-on-computer"></a>V počítači není nainstalována komponenty modelu COM

Pokud uživatel byl přidán odkaz na komponentu modelu COM a druhý uživatel pokusí spustit kód na počítači, který nemá tato součást nainstalována, druhý uživatel se zobrazí chyba, odkaz je poškozený. Instalace součásti v druhém počítači bude opravte chybu. Další informace o tom, jak použít odkazy na komponenty modelu COM v projektech najdete v tématu [interoperabilita modelů COM v aplikacích .NET Framework](/dotnet/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications).

## <a name="see-also"></a>Viz také

[Stránka Odkazy, Návrhář projektu (Visual Basic)](../ide/reference/references-page-project-designer-visual-basic.md)
