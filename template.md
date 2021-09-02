# Heading 1

## Heading 2

### Heading 3

## Body Text

For body text just plain write the sentences this way.

For bulleted points

*   1st point
*   2nd point

For numbered list

1.  1st point
2.  2nd point

To put links - [Website](https://erc-bpgc.github.io/)

To put images -

<center>![image](docs/mechanical/images/drive0.png){: style="height:350px}</center>

Note: This image tag works for mkdocs and might not be apparent by other md interpreters.

To put maths -

$$ \dot{q} = \begin{bmatrix} \dot{\phi}\\ \dot{x}\\ \dot{y}\\ \dot{\psi} \end{bmatrix} = \begin{bmatrix} (tan\psi)/l & 0\\ cos\phi & 0\\ sin\phi & 0\\ 0 & 1 \end{bmatrix} \begin{bmatrix} v\\ \omega \end{bmatrix} $$

For more maths in markdown refer to [this](https://rpruim.github.io/s341/S19/from-class/MathinRmd.html) or any other online markdown maths.

Also refer to [mkdocs documentation](https://www.mkdocs.org/user-guide/writing-your-docs/) for more details.

For localhost testing -

```shell:
python -m mkdocs serve
```
