# [cite_start]HAND Plugin [cite: 1]

[cite_start]HAND é um plugin para a geração do raster Height Above Nearest Drainage (altura acima do ponto drenante mais próximo) a partir de um Modelo Digital de Elevação (MDE), bacia hidrográfica, raster de direção de fluxo e rede de drenagem[cite: 1].

## [cite_start]Descrição [cite: 2]

[cite_start]O plugin calcula o raster HAND, que representa, para cada pixel do MDE, a diferença vertical entre a sua elevação e a elevação do pixel drenante mais próximo (o pixel da rede de drenagem para o qual ele escoa)[cite: 2]. [cite_start]Este produto é amplamente utilizado em análises de susceptibilidade a inundações, modelagem hidrológica e mapeamento de planícies aluviais[cite: 3].

[cite_start]O processamento pode ser executado localmente, invocando rotinas em Python/Fortran, ou através de um backend que recebe os arquivos via HTTP e retorna o GeoTIFF resultante[cite: 4].

## [cite_start]Requisitos [cite: 5]

* [cite_start]QGIS 3.22+ [cite: 5]
* [cite_start]Python 3.9+ (compatível com QGIS/OSGeo4W) [cite: 5]
* [cite_start]GDAL (>=3.8) com bindings Python (osgeo.gdal) [cite: 5]
* [cite_start]NumPy [cite: 5]
* [cite_start]O separador de casas decimais deve ser o ponto (`.`) e não a vírgula (`,`)[cite: 6].

## [cite_start]Uso no QGIS [cite: 7]

1.  [cite_start]Inicie o plugin através do menu `Plugins → HAND Plugin`[cite: 7].
2.  [cite_start]Selecione os arquivos de entrada (inputs)[cite: 8]:
    * [cite_start]Modelo Digital de Elevação - MDE (raster GeoTIFF) [cite: 8]
    * [cite_start]Bacia Hidrográfica (raster GeoTIFF) [cite: 8]
    * [cite_start]Direção de fluxo (raster GeoTIFF) [cite: 8]
    * [cite_start]Rede de drenagem (raster GeoTIFF) [cite: 8]
3.  [cite_start]Clique no botão `Gerar HAND`[cite: 8].

[cite_start]O plugin irá chamar a rotina HAND desenvolvida em Fortran[cite: 9]. [cite_start]Ao finalizar, um GeoTIFF com o resultado do HAND será gerado e adicionado automaticamente ao projeto atual do QGIS[cite: 9].

## [cite_start]Licença [cite: 10]

[cite_start]MIT License [cite: 10]  
[cite_start]Copyright (c) 2025 <João Vitor Lima & Adriano Paz> [cite: 10]
>>>>>>> b4d528e (feat: add HAND Plugin to repo)
