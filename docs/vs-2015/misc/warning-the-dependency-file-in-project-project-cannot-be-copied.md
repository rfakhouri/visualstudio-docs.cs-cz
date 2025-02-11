---
title: 'Upozornění: závislost &#39;souboru&#39; v projektu &#39;projektu&#39; nelze zkopírovat do běhového adresáře, protože by přepsala odkaz &#39;souboru. &#39; | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
f1_keywords:
- vs.tasklisterror.copy_version_warning
ms.assetid: 116819f3-a4d4-48b5-9e71-7c54660d38ef
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8865a1509016a51f30913e51c06e2bcc63912013
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694248"
---
# <a name="warning-the-dependency-39file39-in-project-39project39-cannot-be-copied-to-the-run-directory-because-it-would-overwrite-the-reference-39file39"></a>Upozornění: závislost &#39;souboru&#39; v projektu &#39;projektu&#39; nelze zkopírovat do běhového adresáře, protože by přepsala odkaz &#39;souboru.&#39;
Dojde ke konfliktu mezi závislosti víc souborů odlišné sestavení se stejným názvem, mají být zkopírovány do adresáře bin pro spuštění aplikace. Je schopen vyřešit konflikt, protože jednu ze závislostí je primární odkaz běhového adresáře.  
  
 Tuto položku seznamu úkolů dvojitým kliknutím přejdete na uzel primárního odkazu, který je v konfliktu.  
  
 K tomuto upozornění dochází, když došlo ke konfliktu závislostí, ale pracovali kolem něj tak, že přidáte jednu ze závislostí konfliktní jako odkaz. Nebo jste může mít odkaz na verzi 1 a pak přidá druhý odkaz které se odkazuje na první odkaz verze 2.  
  
 To znamená, že k této chybě dochází, protože projekty v řešení máte odkazy na sebe navzájem, ale nebyly odkazy vytvořeny jako odkazy na soubory (pomocí **Procházet** tlačítko [přidat odkaz](https://msdn.microsoft.com/2feb0fe2-0805-4cc9-8cba-b0315849dfb7) dialogového okna pole), nikoli odkazy typu projekt na projekt (pomocí **projektu** kartě **přidat odkaz** dialogové okno). Výhodou odkazu typu projekt na projekt je, že vytvoří závislost mezi projekty v systému sestavení tak, aby závislý projekt bude vytvořen, jestliže se změnil od posledního odkazujícího projektu. Odkaz na soubor nevytváří závislost sestavení, takže je možné sestavit odkazující projekt bez vytváření závislého projektu a odkaz se může stát zastaralým; Projekt může odkazovat na dřívější sestavené verze projektu. Výsledkem může být několik verzí jednoho souboru knihovny DLL požadovaným v adresáři bin, což není možné a má za následek tato chybová zpráva.  
  
 Tato zpráva se zobrazí pokaždé, když dojde ke konfliktu v adresáři bin aplikace nemusí fungovat správně. I v případě, že jste už pracovali vyřešit tento problém, se stále zobrazí toto upozornění, protože systém projektu nemůže určit, zda verzi závislosti bude správně fungovat se všemi součástmi.  
  
 **Chcete-li opravit tuto chybu**  
  
- Kopírování souborů sestavení jednu (nebo nula) do adresáře bin, což lze provést vložením soubory sestavení do globální mezipaměti sestavení. Globální mezipaměti sestavení řeší konflikty názvů souborů. Žádné místní kopie souboru sestavení bude proveden, protože modul common language runtime ví, jak najít sestavení v globální mezipaměti sestavení. Další informace najdete v tématu [práce se sestaveními a s globální pamětí sestavení](https://msdn.microsoft.com/library/8a18e5c2-d41d-49ef-abcb-7c27e2469433) a [Chyba: závislost 'file' v projektu 'project' nelze zkopírovat do běhového adresáře, protože by vznikl konflikt se závislostí ' Soubor '](/visualstudio/misc/error-dependency-file?view=vs-2015).  
  
## <a name="see-also"></a>Viz také  
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)   
 [Globální mezipaměť sestavení](https://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)   
 [Postupy: Vytváření a odebírání závislostí projektu](../ide/how-to-create-and-remove-project-dependencies.md)