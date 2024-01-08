# Preco_Imovel_IA
 ETAPAS QUE SERÃO ANALISADAS:

 Entendimento do desafio
 
  Entendimentoda Empresa/Área
 
 Extração/Obtenção de daos
 
 Ajustes de Dados (Limpeza de Dados)
 
 Análise Explorativa
 
 Modelagem + Algorítmo
 
 Interpretaçãodos Resultados
 
 Deploy/Produção

CONTEXTO:

No Airbnb, qualquer pessoa que tenha um quarto ou um imóvel de qualquer tipo (apartamento, casa, chalé, pousada, etc.) pode ofertar o seu imóvel para ser alugado por diária.

Você cria o seu perfil de host (pessoa que disponibiliza um imóvel para aluguel por diária) e cria o anúncio do seu imóvel.

Nesse anúncio, o host deve descrever as características do imóvel da forma mais completa possível, de forma a ajudar os locadores/viajantes a escolherem o melhor imóvel para eles (e de forma a tornar o seu anúncio mais atrativo)

Existem dezenas de personalizações possíveis no seu anúncio, desde quantidade mínima de diária, preço, quantidade de quartos, até regras de cancelamento, taxa extra para hóspedes extras, exigência de verificação de identidade do locador, etc.

OBJETIVO:

Construir um modelo de previsão de preço que permita uma pessoa comum que possui um imóvel possa saber quanto deve cobrar pela diária do seu imóvel.
Ou ainda, para o locador comum, dado o imóvel que ele está buscando, ajudar a saber se aquele imóvel está com preço atrativo (abaixo da média para imóveis com as mesmas características) ou não.


O QUE TEMOS DISPONÍVEIS, INSPIRAÇÕES E CRÉDITOS

As bases de dados foram retiradas do site kaggle: https://www.kaggle.com/allanbruno/airbnb-rio-de-janeiro

As bases de dados são os preços dos imóveis obtidos e suas respectivas características em cada mês.
Os preços são dados em reais (R$)
Temos bases de abril de 2018 a maio de 2020, com exceção de junho de 2018 que não possui base de dados.

EXPECTATIVAS INICIAIS:

Acredito que a sazonalidade pode ser um fator importante, visto que meses como dezembro costumam ser bem caros no RJ.

A localização do imóvel deve fazer muita diferença no preço, já que no Rio de Janeiro a localização pode mudar completamente as características do lugar (segurança, beleza natural, pontos turísticos).

Adicionais/Comodidades podem ter um impacto significativo, visto que temos muitos prédios e casas antigos no Rio de Janeiro.

Vamos descobrir o quanto esses fatores impactam e se temos outros fatores não tão intuitivos que são extremamente importantes.

Explicação do Problema e do objetivo

Consiolidar a base de dados em cada coluna

Passo 1 - Explicação do Problema e do objetivo.

Passo 2 - Importat  a Base de Dados.

Passo 3 - Consolidar a Base de Dados.

Passo 4 - Se tiver muitas colunas, identificar quais são possíveis excluir.

Passo 5 - Tratar valores faltando.

Passo 6 - Verificar tipos de Dados emcada coluna

Passo 7- Análise Exploratória e Tratar Outliers

         * Dados Numéricos Contínuos e Discretos
         
         * Dadows de Trxtos (Categorias)
         
         * Dados de Listas
         
         * Dados de Mapa
PSSSO 8 - Ecoding

         * Dados True ou False
         
         * Dados categoria Texto
         
Passo 9 - Modelo Previsão

         * Métricas de Previsão
         
         * Definição do Tipo de Modelo
         
         * Escolhas dos Modelos a Testar
         
         * Treino e avalioação
         
Passo 10 - Snálise do Meçhor Modelo

Passo 11 - Ajustes do Melhor Modelo

Análise Exploratória e Tratar Outliiers

    -Dados Numéricos Contínuos e Discretor
    
    -Dados de Texto (Categorias)
    
    -Dados de Lista
    
    -Dados de Mapa

Passo 2 - Importat  a Base de Dados.
     Como a nossa base de dados está apresentanda por mês vamos consolidá-la par aque possamos ter uma única tabela, ou seja, uma única base de dados.

Passo 4 - Se tiver muitas colunas, identificar quais são possíveis excluir.

      Colunas origiária do banco de dados:
['id', 'listing_url', 'scrape_id', 'last_scraped', 'name', 'summary', 'space', 'description', 'experiences_offered', 'neighborhood_overview', 'notes', 'transit', 'access', 'interaction', 'house_rules', 'thumbnail_url', 'medium_url', 'picture_url', 'xl_picture_url', 'host_id', 'host_url', 'host_name', 'host_since', 'host_location', 'host_about', 'host_response_time', 'host_response_rate', 'host_acceptance_rate', 'host_is_superhost', 'host_thumbnail_url', 'host_picture_url', 'host_neighbourhood', 'host_listings_count', 'host_total_listings_count', 'host_verifications', 'host_has_profile_pic', 'host_identity_verified', 'street', 'neighbourhood', 'neighbourhood_cleansed', 'neighbourhood_group_cleansed', 'city', 'state', 'zipcode', 'market', 'smart_location', 'country_code', 'country', 'latitude', 'longitude', 'is_location_exact', 'property_type', 'room_type', 'accommodates', 'bathrooms', 'bedrooms', 'beds', 'bed_type', 'amenities', 'square_feet', 'price', 'weekly_price', 'monthly_price', 'security_deposit', 'cleaning_fee', 'guests_included', 'extra_people', 'minimum_nights', 'maximum_nights', 'calendar_updated', 'has_availability', 'availability_30', 'availability_60', 'availability_90', 'availability_365', 'calendar_last_scraped', 'number_of_reviews', 'first_review', 'last_review', 'review_scores_rating', 'review_scores_accuracy', 'review_scores_cleanliness', 'review_scores_checkin', 'review_scores_communication', 'review_scores_location', 'review_scores_value', 'requires_license', 'license', 'jurisdiction_names', 'instant_bookable', 'is_business_travel_ready', 'cancellation_policy', 'require_guest_profile_picture', 'require_guest_phone_verification', 'calculated_host_listings_count', 'reviews_per_month', 'ano', 'mes', 'minimum_minimum_nights', 'maximum_minimum_nights', 'minimum_maximum_nights', 'maximum_maximum_nights', 'minimum_nights_avg_ntm', 'maximum_nights_avg_ntm', 'number_of_reviews_ltm', 'calculated_host_listings_count_entire_homes', 'calculated_host_listings_count_private_rooms', 'calculated_host_listings_count_shared_rooms']


Colunas a serem excluídas:
    id - não contribui com o objetivo
    listing_url -  não contribui com o objetivo
    scrape_id -  não contribui com o objetivo
    last_scraped - Já foi criada as colunaS da data da informação
    name, summary, space, description - campos de textos desnecessários
    experiences_offered - Apresenta valores vazios
    neighborhood_overview, notes, transit, access, interaction, house_rules, thumbnail_url, medium_url - são explicações
    picture_url, 	xl_picture_url,	host_id, 	host_url, 	host_name, host_since, host_location - não contribuiem com o objetivo
    host_about - não contribui com o objetivo








