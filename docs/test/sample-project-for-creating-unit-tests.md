---
title: "Ukázkový projekt testů jednotek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
ms.assetid: db80aaf2-0652-4d3f-a8c5-2a98fd8502a2
caps.latest.revision: "30"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 85abc33ab5dd1253402e020c3b77c1b639e5ae44
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sample-project-for-creating-unit-tests"></a>Ukázkový projekt testů jednotek
Tento ukázkový kód je určen pro použití v následující kurzy:  
  
-   [Návod: Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). Tento názorný postup vás provede kroky pro vytváření a přizpůsobení testování částí, jejich spuštění a podívejte se na výsledky testu.  
  
-   [Návod: Spuštění testů a zobrazit pokrytí kódu](http://msdn.microsoft.com/en-us/d4aab8e2-2140-4975-b4e3-41ef3fa944c8). Tento návod ukazuje, jak zobrazit data pro pokrytí kódu, který zobrazuje podíl vašeho projektu kódu, která se testuje.  
  
-   [Návod: použití nástroje testů z příkazového řádku](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). V tomto návodu můžete pomocí nástroje příkazového řádku MSTest.exe spouštět testy a zobrazit výsledky.  
  
## <a name="sample-code"></a>Ukázkový kód  
 Pouze touto úmyslnou chybou v této ukázce je, že metodu v debetní "m_balance += částka" by měl mít minus, není plus přihlášení před symbolem rovná se.  
  
```  
using System;   
  
namespace BankAccountNS  
{  
    /// <summary>   
    /// Bank Account demo class.   
    /// </summary>   
    public class BankAccount  
    {  
        private string m_customerName;  
  
        private double m_balance;  
  
        private bool m_frozen = false;  
  
        private BankAccount()  
        {  
        }  
  
        public BankAccount(string customerName, double balance)  
        {  
            m_customerName = customerName;  
            m_balance = balance;  
        }  
  
        public string CustomerName  
        {  
            get { return m_customerName; }  
        }  
  
        public double Balance  
        {  
            get { return m_balance; }  
        }  
  
        public void Debit(double amount)  
        {  
            if (m_frozen)  
            {  
                throw new Exception("Account frozen");  
            }  
  
            if (amount > m_balance)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            if (amount < 0)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            m_balance += amount; // intentionally incorrect code  
        }  
  
        public void Credit(double amount)  
        {  
            if (m_frozen)  
            {  
                throw new Exception("Account frozen");  
            }  
  
            if (amount < 0)  
            {  
                throw new ArgumentOutOfRangeException("amount");  
            }  
  
            m_balance += amount;  
        }  
  
        private void FreezeAccount()  
        {  
            m_frozen = true;  
        }  
  
        private void UnfreezeAccount()  
        {  
            m_frozen = false;  
        }  
  
        public static void Main()  
        {  
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);   
  
            ba.Credit(5.77);  
            ba.Debit(11.22);  
            Console.WriteLine("Current balance is ${0}", ba.Balance);  
        }  
  
    }  
}  
```  
  
 / * Společností, organizací, produktů, názvů domén, e-mailové adresy, loga, osoby, místa a události použité v ukázkách jsou smyšlené.  Žádné spojení se skutečnou společností, organizace, produktu, název domény, e-mailovou adresu, logem, osoba, místech nebo události je určený nebo událostmi. \*/  
  
## <a name="working-with-the-code"></a>Práce s kódem  
 Pro práci s tímto kódem je nejprve nutné pro něj vytvořit projekt v sadě [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Postupujte podle kroků v části "Příprava návodu" [návod: vytváření a spuštěné testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytváření a spouštění testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)   
 [Návod: Spuštění testů a zobrazit pokrytí kódu](http://msdn.microsoft.com/en-us/d4aab8e2-2140-4975-b4e3-41ef3fa944c8)   
 [Návod: použití nástroje testů z příkazového řádku](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
