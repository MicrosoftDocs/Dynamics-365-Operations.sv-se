---
title: Skapa ett Azure Storage-konto och ett nyckelvalv
description: I det här avsnittet beskrivs hur du skapar ett Azure Storage-konto och nyckelvalv.
author: gionoder
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23fec7a00d800719e1a7d2c90f9d0977d56be038
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463871"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Skapa ett Azure Storage-konto och ett nyckelvalv

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra stegen i det här ämnet måste du se till att följande uppgifter har slutförts:

- Skapa en nyckelvalvresurs i Azure. Mer information om mått finns i [Om Azure Key Vault](/azure/key-vault/general/overview).
- Skapa ett Azure Storage-konto (Blob Storage). Mer information finns i [Underhålla Azure Storage-kontot](/azure/storage/blobs/).

## <a name="overview"></a>Översikt

I det här avsnittet ska du utföra två huvudsteg:

- Konfigurera Azure Storage-kontot för att hämta lagringskontots URI.
- Ställ in nyckelvalvet för att lagra lagringskontots URI.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Konfigurera Azure Storage-kontot för att hämta lagringskontots URI

1. Öppna det lagringskonto som du vill använda med tillägget e-fakturering.
2. Gå till **Datalagring** > **Behållare** och skapa en ny behållare.
3. Ange ett namn på behållaren och ställ in fältet **Offentlig åtkomstnivå** på **Privat (ingen anonym åtkomst)**.
4. Öppna behållaren och gå till **Inställningar** > **Åtkomstpolicy**.
5. Välj **Lägg till policy** om du vill lägga till en lagrad åtkomstpolicy.
6. Ange fältet **Identifierare** och **Behörigheter** efter behov. I fältet **Behörigheter** bör du välja alla behörigheter.

    ![Bevilja behörighet för Blob Storage.](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Ange start- och utgångsdatum. Utgångsdatumet måste vara i framtiden.
8. Klicka på **OK** om du vill spara policy och spara sedan ändringarna i behållaren.
9. Gå till **Inställningar** > **Delade åtkomsttokens** och ställ in fältvärdena. 
10. Ange start- och slutdatum. Slutdatumet måste vara i framtiden.
11. I fältet **Behörighet** välj följande behörigheter: **Läsa**, **Lägga till**, **Skapa**, **Skriva**, **Ta bort** och **Lista**. 
12. Välj **Generera SAS-token och URL**.
13. Kopiera och lagra värdet i fältet **Blob SAS URL**. Det här värdet används i nästa procedur och kallas för *Signatur för delad åtkomst URI*.

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Ställ in nyckelvalvet för att lagra lagringskontots URI

1. Öppna det nyckelvalv som du vill använda med e-fakturering.
2. Gå till **Inställning** \> **Hemligheter** och välj sedan **Generera/importera** om du vill skapa en ny hemlighet.
3. På sidan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.
4. Ange namnet på hemligheten. Det här namnet används under installationen av tjänsten i RCS (Regulatory Configuration Service) och kommer att kallas *nyckelvalvets hemliga namn*.
5. Ange den URI för signatur för delad åtkomst som du kopierade i den föregående proceduren i fältet **Värde** och välj sedan **Skapa**.
6. Ställ in åtkomstprincipen så att e-fakturering på den korrekta nivån för säker åtkomst till den hemlighet som du har skapat. Gå till **Inställningar \> Åtkomstprinciper** och välj **Lägg till åtkomstprincip**.
7. Ange de hemliga behörigheterna för åtgärderna **Hämta** och **Lista**.

    ![Bevilja tjänsteåtkomst.](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Ange certifikatbehörigheter för åtgärderna **Hämta** och **Lista**.

    ![Bevilja certifikatbehörighet.](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. I fältet **Välj huvudkonto**, välj **Inget valt**.
10. I dialogrutan **Primär** välj primär genom att lägga till **Tjänst för e-fakturering**.
11. Välj **Lägg till** och välj sedan **Spara**.
12. På sidan **Översikt** kopiera värdet **DNS-namn** för nyckelvalvet. Det här värdet kommer att användas under installationen av tjänsten i RCS och kallas *nyckelvalv-URI*.

> [!NOTE]
> Om du vill ha mer säkerhet på lagringskontot konfigurerar du Azure Azure for Storage.
> 
> Mer information finns i [Introduktion till Azure Defender for Storage](/azure/security-center/defender-for-storage-introduction).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
