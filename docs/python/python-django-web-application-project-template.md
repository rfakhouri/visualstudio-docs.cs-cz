---
title: Šablona projektu webového rozhraní Django pro jazyk Python
description: Přehled šablony sady Visual Studio pro webové aplikace napsané v Pythonu pomocí rozhraní Django.
ms.date: 07/13/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 5c5b64e6f14ef8a6d8015f27252374e54a6dd764
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="django-web-project-template"></a>Šablona webového projektu Django

[Django](https://www.djangoproject.com/) je určená pro vývoj webů rychlé, zabezpečené a škálovatelné vysoké úrovně rozhraní Python. Podpora jazyka Python v sadě Visual Studio poskytuje šablona projektu nastavení struktury založené na rozhraní Django webové aplikace. Abyste mohli použít šablonu v sadě Visual Studio, vyberte **soubor > Nový > projekt**, vyhledejte "Django" a vyberte **webový projekt Django** šablony. Výsledný projekt zahrnuje často používaný kód a také výchozí databáze SQLite. **Prázdný webový projekt Django** šablony je podobné však nezahrnuje databázi.

Visual Studio poskytuje úplné IntelliSense pro projekty Django:

- Proměnné kontext je předán do šablony:

    ![IntelliSense pro kontext proměnné](media/template-django-intellisense.png)

- Označování a filtrování pro obě built-ins a uživatelem definované:

    ![IntelliSense pro značky a filtry](media/template-django-intellisense-filter.png)

- Pro vložených šablon stylů CSS a JavaScript zvýrazňování syntaxe:

    ![IntelliSense šablon stylů CSS](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio také poskytuje úplné [ladění podporu](debugging-python-in-visual-studio.md) pro projekty Django: 

![Zarážky](media/template-django-debugging.png)

Je obvyklé, Django projektů se mají spravovat prostřednictvím jejich `manage.py` souboru, který se předpokládá, který následuje Visual Studio. Pokud zastavíte pomocí tento soubor jako vstupní bod, v podstatě rozdělit souboru projektu. V takovém případě budete muset [znovu vytvořit projektu z existujících souborů](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) bez označení jako projekt Django.

## <a name="django-management-console"></a>Konzola pro správu Django

Konzola pro správu Django přistupuje prostřednictvím různých příkazy **projektu** nabídky nebo kliknutím pravým tlačítkem na projekt v Průzkumníku řešení.

- **Otevřete prostředí Django...** : otevře prostředí v kontextu vaší aplikace, která umožňuje pracovat s modely "

    ![Konzola](media/template-django-console-shell.png)

- **Django synchronizace DB**: provede `manage.py syncdb` v interaktivních okna:

    ![Konzola](media/template-django-console-sync-db.png)

- **Shromažďovat statické**: provede `manage.py collectstatic --noinput` zkopírovat všechny statické soubory do cestu určenou položkou `STATIC_ROOT` ve vaší `settings.py`. Všimněte si, že když [publikování do služby Microsoft Azure](python-web-application-project-templates.md#publishing-to-azure-app-service), statické soubory jsou shromažďovány automaticky v rámci operace publikování.

    ![Konzola](media/template-django-console-collect-static.png)

- **Ověření**: provede `manage.py validate`, které sestavy všechny chyby ověřování nainstalovaný modely určeného `INSTALLED_APPS` ve vaší `settings.py`:

    ![Konzola](media/template-django-console-validate.png)