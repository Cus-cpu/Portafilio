# DESFIBRILADORES
Los desfibriladores externos automáticos (DEA) son dispositivos electrónicos comúnmente utilizados para tratar ciertos tipos de arritmias. Son capaces de analizar el ritmo cardiaco y detectar si el ritmo presente es susceptible a un tratamiento cardiaco o no mediante una descarga eléctrica. Estos dispositivos se pueden encontrar comúnmente en lugares públicos de forma estratégica de tal forma que puedan ser utilizados por las personas que presencian una parada cardiaca e inicien de forma inmediata la reanimación de la persona afectada.

# PROBLEMA
Para que estos dispositivos sean realmente efectivos, su uso debe realizarse de manera inmediata. Con lo cual, es de suma importancia que cualquier persona sea capaz de usarlo sin necesidad de conocimientos previos. Por ello, estos dispositivos constan de un algoritmo predictivo de clasificación que detecta, si existe o no alguna anomalía cardiaca.

# DESARROLLO
Se van a utilizar dos dataset  con 30 parámetros obtenidos a partir de electrocardiogramas (ECG), entre los que tenemos la amplitud, el valor medio o el área. Uno de los datasets sera el de train y otro el de test.
Primero se llevará a cabo un EDA donde se verá la relación entre las variables y las distribuciones de estas. 
Posteriormente, se plantea utilizar distintos algoritmos buscando obtener el mejor parendizaje y que por tanto, prediga de forma más precisa si es necesaria realizar una descarga eléctrica. Los algoritmos usados son:
- Regresión logística
- XGBoost
- Random forest
- SVC
He modificado los hiperparámetros iterando miles de veces haciendo uso del pipeline y quedándome con la mejor combinación

# RESULTADOS

Dentro del EDA lo que más destaca es la gráfica de correlación de variables. Este nos indica bastante correlación entre las variables y nuestra variable target (VF) como se puede ver en la
[Matriz de correlacion](projects/1. Desfibriladores/images/Matriz de correlacion.PNG)

Para el aprendizaje se obtienen los siguientes valores de accuracy para el train, el test. También se ha incluido el área bajo la curva (AUC) que es una representación escalar del rendimiento esperado de un clasificador.
| Modelo | Train | Test | AUC |
| ------------ | ------------ | ------------ | ------------ |
| Regresión logística    | -    | 0.990  | 0.997   |
| XGBoost    | 0.971  | 0.980    | 0.975    |
| Random forest    | 0.964   | 0.985   | 0.977    |
| SVC  | 0.957    | 0.985    | 0.977    |

De esta tabla se peude extraer que el mejor moedelo para este caso es la regresión logística ya que tiene el mejor valor de predicción y además es un modelo sencillo lo que lo hace más fácil de manejar y menos costoso computacionalmente.
