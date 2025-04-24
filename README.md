# Feed_forward_Cifar-100

# Proyecto de aprendizaje Cifar-100

En este proyecto desarrollaremos un clasificador de imágenes basado en Deep Learning utilizando el conjunto de datos CIFAR-100. La solución combina procesamiento de imágenes, redes neuronales profundas (MLP) y una interfaz web interactiva mediante Gradio para facilitar la visualización y uso del modelo.

# ¿Que es cifar-100?

CIFAR-100 es un conjunto de datos ampliamente utilizado en el campo del Deep Learning. Contiene 60,000 imágenes (50,000 entrenamiento - 10,000 prueba) a color de tamaño 32x32 píxeles, distribuidas en 100 clases diferentes, con 600 imágenes por clase (500 de entrenamiento - 100 de prueba). Estas clases incluyen objetos variados como animales, vehículos, árboles, frutas, instrumentos, etc.

# ¿Qué haremos técnicamente?

**1.Carga y Preprocesamiento de Datos**  
   - Cargaremos el conjunto de datos CIFAR-100.
   - Redimensionaremos y normalizaremos las imágenes.
   - Convertiremos las etiquetas a formato categórico (one-hot encoding).
   - Aplanaremos las imágenes para pasarlas a una red totalmente conectada (MLP).

**2.Construcción del Modelo**  
   - Diseñaremos una red neuronal MLP (Multilayer Perceptron).
   - Usaremos capas densas con funciones de activación ReLU.
   - Añadiremos Dropout y regularización L2.
   - Finalizaremos con una capa `softmax` para clasificar entre 100 clases.

**3.Entrenamiento del Modelo**  
   - Compilaremos el modelo con optimizador SGD (con Nesterov), pérdida `categorical_crossentropy` y métrica `accuracy`.
   - Usaremos callbacks como `EarlyStopping`, `ModelCheckpoint` y `TensorBoard`.
   - Entrenaremos con validación y ajustaremos el learning rate dinámicamente.

**4.Evaluación y Métricas**  
   - Analizaremos el rendimiento del modelo con:
   - Matriz de confusión
   - Curvas de precisión y recall
   - Curvas ROC/AUC
   - Histogramas de desempeño por clase
   - Identificaremos las clases con mejor y peor desempeño.

**5.Interfaz Interactiva con Gradio**  
   - Implementaremos una interfaz web sencilla con Gradio.
   - Permitiremos al usuario cargar imágenes desde su dispositivo.
   - El modelo devolverá la clase predicha como salida textual.

# Pip utilizado
```
!pip install gradio
```
# Ventajas de usar gradio

- Fácil de compartir: El enlace público permite compartir con cualquier persona.
- Feedback visual: Muestra las probabilidades de las principales predicciones.
- Interfaz amigable: Permite a las personas interactuar con el modelo sin la necesidad de escribir código.

# Conclusión

**1.Rendimiento General:**

   ❌ El modelo MLP no logró un buen rendimiento para CIFAR-100.

**2.Limitaciones:**
   - Las MLPs procesan imágenes aplanadas, perdiendo la información espacial.
   - Para imágenes, las redes convolucionales (CNN) suelen tener mejor rendimiento.
   - El modelo puede tener dificultades con objetos rotados o en diferentes posiciones.
   -El modelo tiene overfitting.

**3.Mejoras Potenciales:**
   - Probar arquitecturas más complejas (más capas, más unidades).
   - Implementar técnicas de aumentación de datos (rotaciones, volteos, zoom).
   - Ajustar los hiperparámetros mediante búsqueda de cuadrícula o aleatoria.
   - Migrar a una arquitectura CNN para mejorar significativamente el rendimiento.

**4.Comparación con otro tipo de arquitecturas:**
   - Convolucionales

# Documentación y enlaces útiles
-[Documentación de Cifar-100](https://paperswithcode.com/dataset/cifar-100)
  
-[Documentación de Keras](https://keras.io/api/optimizers/)
