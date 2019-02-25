# deoplete-citation.vim

```
# from importする必要あり
from pybtex.database import parse_file

file_path = '~/.pandoc/library.bib'
# BibliographyDataクラスオブジェクトを作る
bib_file = parse_file(file_path, bib_format='bibtex')

# entriesで全ての書誌情報がreturnされる
# print(bib_file.entries)

# entriesは辞書型なので，keys()でcitation keyのリストを得られる
# print(bib_file.entries.keys())

# entriesは辞書型なので，citation keyをkeyにして書誌情報の内容がreturnされる
print(bib_file.entries['Ishibashi2019'], "\n")

# Entry(
#     'article',
#     fields=[
#         ('doi', '10.1111/gtc.12669'),
#         ('issn', '1356-9597'),
#         ('journal', 'Genes to Cells'),
#         ('month', 'feb'),
#         ('pages', 'gtc.12669'),
#         ('pmid', '30624823'),
#         ('title', '{E and ID proteins regulate cell chirality and left–right asymmetric development in Drosophila}'),
#         ('url', 'http://doi.wiley.com/10.1111/gtc.12669 https://onlinelibrary.wiley.com/doi/abs/10.1111/gtc.12669'),
#         ('year', '2019')
#         ],
#     persons=OrderedCaseInsensitiveDict([
#         ('author', [
#             Person('Ishibashi, Tomoki'),
#             Person('Hatori, Ryo'),
#             Person('Maeda, Reo'),
#             Person('Nakamura, Mitsutoshi'),
#             Person('Taguchi, Tomohiro'),
#             Person('Matsuyama, Yoko'),
#             Person('Matsuno, Kenji')
#             ])
#         ])
#     )

# 著者以外の情報がfieldsに入っている
print(bib_file.entries['Ishibashi2019'].fields, "\n")
# たとえばタイトルや雑誌名を取り出せる
print(bib_file.entries['Ishibashi2019'].fields['title'], "\n")
print(bib_file.entries['Ishibashi2019'].fields['journal'], "\n")
print(bib_file.entries['Ishibashi2019'].fields['year'], "\n")

# 著者情報はauthorにリストで入っている
print(bib_file.entries['Ishibashi2019'].persons['author'], "\n")

# first authorやlast authorについても取り出せる
print(bib_file.entries['Ishibashi2019'].persons['author'][0], "\n")
print(bib_file.entries['Ishibashi2019'].persons['author'][-1], "\n")
print(bib_file.entries['Ishibashi2019'].persons['author'][0].first_names, "\n")
print(bib_file.entries['Ishibashi2019'].persons['author'][1].last_names, "\n")
```
