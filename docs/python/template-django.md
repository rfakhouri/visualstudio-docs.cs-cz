---
title: "Šablona projektu webového rozhraní Django pro jazyk Python v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: b9a6c3240075107edfc5109fa6c62aaf6c23d92b
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="django-web-project-template"></a>Šablona projektu webového rozhraní Django

[Django](https://www.djangoproject.com/) je určená pro vývoj webů rychlé, zabezpečené a škálovatelné vysoké úrovně rozhraní Python. Podpora jazyka Python v sadě Visual Studio poskytuje šablona projektu nastavení struktury založené na rozhraní Django webové aplikace. Abyste mohli použít šablonu v sadě Visual Studio, vyberte **soubor > Nový > projekt**, vyhledejte "Django" a vyberte **webový projekt Django** šablony. Výsledný projekt zahrnuje často používaný kód a také výchozí databáze SQLite. **Prázdný webový projekt Django** šablony je podobné však nezahrnuje databázi.

Visual Studio poskytuje úplné IntelliSense pro projekty Django:

- Proměnné kontext je předán do šablony:

    ![IntelliSense pro kontext proměnné](media/template-django-intellisense.png)

- Označování a filtrování pro obě built-ins a uživatelem definované:

    ![IntelliSense pro značky a filtry](media/template-django-intellisense-filter.png)

- Pro vložených šablon stylů CSS a JavaScript zvýrazňování syntaxe:

    ![CSS IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio také poskytuje úplné [ladění podporu](debugging.md) pro projekty Django: 

![Zarážky](media/template-django-debugging.png)

Je obvyklé, Django projektů se mají spravovat prostřednictvím jejich `manage.py` souboru, který se předpokládá, který následuje Visual Studio. Pokud zastavíte pomocí tento soubor jako vstupní bod, v podstatě rozdělit souboru projektu. V takovém případě budete muset [znovu vytvořit projektu z existujících souborů](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) bez označení jako projekt Django.

## <a name="django-management-console"></a>Konzola pro správu Django

Konzola pro správu Django přistupuje prostřednictvím různých příkazy **projektu** nabídky nebo kliknutím pravým tlačítkem na projekt v Průzkumníku řešení.

- **Otevřete prostředí Django...** : otevře prostředí v kontextu vaší aplikace, která umožňuje pracovat s modely "

    ![Konzola](media/template-django-console-shell.png)

- **Django synchronizace DB**: provede `manage.py syncdb` v interaktivních okna:

    ![Konzola](media/template-django-console-sync-db.png)

- **Shromažďovat statické**: provede `manage.py collectstatic --noinput` zkopírovat všechny statické soubory do cestu určenou položkou `STATIC_ROOT` ve vaší `settings.py`. Všimněte si, že když [publikování do služby Microsoft Azure](template-web.md#publishing-to-azure-app-service), statické soubory jsou shromažďovány automaticky v rámci operace publikování.

    ![Konzola](media/template-django-console-collect-static.png)

- **Ověření**: provede `manage.py validate`, které sestavy všechny chyby ověřování nainstalovaný modely určeného `INSTALLED_APPS` ve vaší `settings.py`:

    ![Konzola](media/template-django-console-validate.png)