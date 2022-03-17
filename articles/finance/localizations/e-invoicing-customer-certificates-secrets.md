---
title: Kundcertifikat och hemligheter
description: I detta ämne beskrivs hur du ställer in kundcertifikat och hemligheter i E-fakturering.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1325cad95e9a6dc470691f5f168439fccaaa78e1
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371814"
---
# <a name="customer-certificates-and-secrets"></a>Kundcertifikat och hemligheter

[!include [banner](../includes/banner.md)]

Om du redan har en Microsoft Azure-referens för nyckelvalv i Regulatory Configuration Service (RCS) kan du skapa referenser till nyckelvalvets certifikat och hemligheter. Om du ännu inte har någon nyckelvalvsreferens, se [Tjänstemiljöer](e-invoicing-service-environments.md) för information om hur du skapar den.

## <a name="create-certificates-and-secrets"></a>Skapa certifikat och hemligheter

Följ dessa steg om du vill skapa och ställa in en certifikat och hemligheter.

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **e-fakturor**.
3. På sidan **Miljökonfiguration** väljer du **Tjänstemiljöer** i åtgärdsfönstret.
4. På sidan **Tjänstemiljöer** väljer du **Parametrar för nyckelvalv** i åtgärdsfönstret.
5. På sidan **Parametrar för nyckelvalv** väljer du en nyckelvalvsreferens innan du i avsnittet **Certifikat** väljer **Lägg till**.
6. I fältet **Namn** anger du namnet för nyckelvalvscertifikatet eller -hemligheten. Mer information finns i [Skapa ett Azure-lagringskonto i Azure-portalen](e-invoicing-create-azure-storage-account-azure-portal.md).
7. Ange en beskrivning i fältet **beskrivning**.
8. I fältet **Typ** väljer du **Certifikat** om du refererar till certifikatet som lagrats i nyckelarkivet. Välj **Hemlighet** om du refererar till den hemlighet som lagras i nyckelvalvet.
9. Välj **Spara**.

> [!NOTE]
> I vissa situationer måste du använda allmänna certifikat som har filnamnstillägget .cer. Key Vault stöder dock inte import och lagring av certifikat av den här typen som nyckelvalvcertifikat. I dessa scenarier ska du spara .cer-filen som en Base-64-kodad X.509 (.CER)-sträng. I en nyckelvalvhemlighet lagrar du sedan strängen som visas mellan raden **BEGIN CERTIFICATE** och raden **END CERTIFICATE** i filen. I servicemiljön bör du fortfarande skapa en referens till Key Vault-posten och ställa in fältet **Typ** på **Certifikat**.

## <a name="create-a-chain-of-certificates"></a>Skapa en certifikatkedja

Om dina lands-/regionspecifika fakturor kräver en certifikatkedja för att tillämpa digitala signaturer eller upprätta en säker (Secure Sockets Layer \[SSL\])-anslutning till externa webbtjänster, skapar du en kedja med certifikat där certifikaten är i följande ordning:

1. Rotcertifikat
2. Mellanliggande certifikat
3. Certifikat för slutanvändare

Rotcertifikatutfärdare (CA) är en betrodd källa till certifikat. Mellanliggande CA-certifikat länkar slutanvändarcertifikaten till CA-rotcertifikaten.

Följ dessa steg om du vill konfigurera en certifikatkedja.

1. På sidan **Key Vault-parametrar** väljer du **Certifikatkedja** i åtgärdsfönstret.
2. Välj **Ny** för att skapa en certifikatkedja.
3. I fältet **Namn** anger du namnet på certifikatkedjan.
4. Ange en beskrivning i fältet **beskrivning**.
5. I avsnittet **Certifikat** väljer du **Lägg till** för att lägga till ett certifikat i kedjan.
6. Använd knappen **Upp** eller **Ner** för att byta certifikatets position i kedjan. Behåll CA-rotcertifikatet längst upp i listan och slutanvändarcertifikatet längst ned.
7. Välj **Spara**.

Du kan skapa så många Key Vault-referenser i RCS som du vill. Kom ihåg att hemligheten för lagringstoken för delad åtkomst (SAS) används för att koppla en given tjänstemiljö till Key Vault-referensen. Du kan referera till Key Vault-certifikat och -hemligheter som lagras i ett nyckellager som även innehåller den hemlighet för lagrings-SAS-token som du använder när du ställer in servicemiljön.
