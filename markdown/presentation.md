name: inverse
layout: true
class: center, middle, inverse
---
# Accelerate

## De la entrega de software al desempeño y rentabilidad organizacional

## La propuesta de [DORA](https://dora.dev/) (DevOps Research and Assessment)

???

Claramente esta charla tiene que ver con DevOps, tema sobre el cual ya tuvimos [una charla hace un par de años](https://makingsense.slack.com/archives/C02BE65EW/p1612366212066700)

En esta oportunidad, luego de dar contexto, voy a tratar de profundizar en una propuesta en particular.

---
name: spiral
layout: false

## Espiral de caída destructiva

???

Cómo muchos términos exitosos, DevOps ya quiere decir demasiadas cosas, así que voy a tratar de describir cual es el problema al que respondió el nacimiento de DevOps, según lo cuenta Gene Kim (ya vamos a hablar más de él luego) en cuatro actos.

En mi carrera, yo también viví situaciones parecidas, aunque a veces los roles no eran exactamente los mismos, creo que puedo sentirme identificado. 

--

### Act 1: IT Ops fixing fragile artifacts

???

La gente de operaciones se entera de problemas o caídas por quejas de clientes, gente de ventas o de otra manera, generalmente no por herramientas de monitoréo y tiene que emparcharlo. Por ejemplo, reiniciando un servidor cuando recibe quejas de que está lento, etc.

Cuando esto ocurre, en paralelo suelen empezar a ocurrir otras cosas: 

* Se empieza a perder cuota de mercado o deja de subir
* Se incumplen compromisos con el mundo exterior (inversores o clientes)
* El promedio de tamaño de pedidos crece

--

### Act 2: The Product Managers

???

Al presentarse problemas de incumplimientos, se hacen planes y compromisos aún más audaces. Gene habla de "art mayors" o "creative writing mayors" que en esta situación suelen definir requerimientos que no son cumplibles.

--

###  Act 3: The Developers

???

En el tercer acto aparecen los developers (caracterizados por Gene, como personas fumando cerca de una advertencia de material explosivo), que dirigidos por proyectos urgentes, que no pueden mover la fecha de entrega, empiezan a tomar atajos, solo se dedican a las features y nada a requerimientos no funcionales.

El código se hace más frágil, los deploys más arduos, llenos de partes móviles.

Para ahorrar tiempo se reduce la cantidad de deployments y **eso es justo lo que
no hay que hacer**.

--

### Act 4: Dev and IT Ops at War

???

Se desata una guerra tribal, la gente de operaciones culpa a los desarrolladores de hacer código frágil, la gente de desarrollo de ser burocráticos y demorar los proyectos.

En mi carrera, yo no lo sentí tanto con gente de operaciones, en algún caso porque en mi rol yo estaba lejos, en otros por la estructura del proyecto, pero si llegue a vivir esto. Algunas veces con diferentes equipos de desarrolladores dentro de un proyecto, o entre los equipos de QA y Devs.

Hay cada vez más trabajo no planificado, parches de los parches y la espiral sigue girando.

--

<hr />

¿Alguien entre los presentes tuvo experiencias parecidas?


---
name: que-es-devops
class: center, middle

# ¿Que es DevOps?

???

¿Seguramente hay presente alguien que pueda dar una definición?

---
name: que-es-devops-2
layout: false

.image-630h[![Definiciones DevOps](definiciones-devops.png)]

???

Hay muchas definiciones, algunas se centran en aspectos técnicos (principalmente relacionados con poner en producción las features en el menor tiempo posible de forma segura), pero en general terminan concluyendo en aspectos culturales.

Para ir acercándonos al objetivo de esta charla veamos la definición propuesta por Google Cloud (quien adquirió en 2018 al proyecto DORA)

Fuentes:

- [Wikipedia](https://en.wikipedia.org/wiki/DevOps)
- [Tips, Tricks, & How to: Become an Elite DevOps Organisation](https://youtu.be/y0M9Z_zSmPo?t=606) (sic)
- [Nuevo repo DevOps de Making Sense](https://github.com/MakingSense/makingsense-devops)
- [DevOps: A Software Architect's Perspective](https://learning.oreilly.com/library/view/devops-a-software/9780134049885/ch01.html#:-:text=DevOps%20is%20a,ensuring%20high%20quality.)

---
name: circulo-virtuoso-1
layout: false
## Círculo virtuoso

.image-scaled[![cultura-devops](cultura-devops.png)]

???

Podríamos considerar que todo comienza desde un aspecto cultural: tenemos que estar de acuerdo en querer tener los cambios en producción cuanto antes. 

Algunas organizaciones tienen incorporado el concepto de Kaizen, pero en muchos casos percibido esto no es percibido un valor obvio. 

Y esto tiene impactos en otras áreas, por ejemplo en el diseño del producto.

Por otro lado, estas prácticas también modifican la cultura de toda la organización porque abren canales de comunicación y brindan un marco "Buttom-Up" para que todos puedan involucrarse en una mejora continua. 

---
name: circulo-virtuoso-2
layout: false
## Círculo virtuoso

[Ver versión actualizada más detallada...](https://dora.dev/pdf/big_friendly_diagram.pdf) .image-scaled[![cultura-devops](overall-research-program.png)]

---
name: dora
layout: false

.image-scaled[![dora-google-accelerate](dora-google-accelerate.png)]

???

Los reportes the "State of DevOps" se hacen desde 2012. Desde el reporte del 2014, Gene Kim, Nicole Forsgren y Jez Humble los continuaron y fueron profundizando y formalizando cada vez más esa investigación. Desde el 2018 este proyecto fue
adquirido por Google e incorporado a Google Cloud.

Además de los reportes, en 2018 publicaron el libro Accelerate donde describen en profundidad su metodología y su propuesta.

Resumiendo (mucho), ellos verificaron que algunas métricas relacionadas con la practica de DevOps son predictores estadísticos de la performance organizacional, es decir que las empresas rentables y sustentables suelen medir bien en esos aspectos. Luego, ellos identificaron capacidades que permiten medir mejor en esos aspecto y proponen maneras de desarrollarlas.

Referencias:

- [Google Cloud Architecture Center](https://cloud.google.com/architecture/devops/)
- [DevOps Research and Assessment](https://dora.dev/)
- [State of DevOps reports](https://dora.dev/publications/)
- [Accelerate](https://www.google.com/books/edition/_/Kax-DwAAQBAJ)


---
name: metrics-1
layout: false
## Cuatro Métricas Clave

.image-scaled[![key-metrics](key-metrics.png)]

???

Al ordenar las organizaciones según su desempeño (dependiendo de la industria), demostraron estadísticamente que estas métricas relacionadas con las practicas de DevOps predicen el desempeño organizacional.

### Lead Time

Desde el commit hasta salir a producción (o en algunos escenarios, el entorno justo anterior).

Estaría bueno medir desde "la idea", o desde que se empezó el desarrollo hasta la salida a producción, pero es una métrica bastante más complicada.

### Deployment Frequency

Cada cuanto tiempo publicamos.

### Change Fail

Cuantas veces luego de publicar a producción hay que aplicar acciones correctivas.

### Time to restore

Tiempo de recuperarse si algo sale mal.

En una organización de alta performance, suele ser igual al _lead time_. En cambio en una organización de baja performance suele haber mucha variabilidad, porque, por ejemplo, en esos casos se saltan validaciones, y eso puede hacer que las cosas sean peor aún.

### Availability

Identificaron que es un predictor más directo de muchas cosas, por ejemplo de cuota de mercado o satisfacción de los clientes, pero no lo toman como _key metric_, tal vez por la dificultad de accionar tan directamente y porque depende de los otros.

---
name: performance-clusters
layout: false
## Performance Clusters

.image-scaled[![performance-clusters](performance-clusters.png)]

???

En base a estas métricas, ellos clasificaron a las organizaciones en:

- Low performers
- Medium performers
- High performers
- Elite

Hay algo interesante en esa comparación entre 2018 y 2019. Claramente muchos de los _high performers_ mejoraron y también algunos de los _low performers_. Pero algunos de los _high performers_ bajaron a _medium performers_. Ellos lo atribuyen a la conformidad o a la falta de "mejora continua": "O todo el tiempo estás mejorando o empeorás."

---
name: fast-or-stable-1
layout: false
## Fast or stable

.image-scaled[![bueno-barato-rapido](bueno-barato-rapido.png)]

???

¿Que opinan de este gráfico?

---
name: fast-or-stable-2
layout: false
## Fast or stable

.image-scaled[![bueno-barato-rapido-falso](bueno-barato-rapido-falso.png)]

???

Podemos decir que en el mediano plazo. Pero no es una novedad, ya lo dijo Deming hace 70 años. Si queremos disminuir los costos y producir más, tenemos que mejorar la calidad.

Las organizaciones de elite publican más rápido y tienen menos fallos. Las organizaciones de baja performance publican más lento, tienen más fallos y tardan más en recuperarse de ellos.

Entonces: hacer bien las cosas no implica que bajemos la velocidad (al menos en el mediano plazo)

---
name: fast-or-stable-3
## Fast or stable

.image-scaled[![is-quality-worth-cost](is-quality-worth-cost.png)]

<https://martinfowler.com/articles/is-quality-worth-cost.html>

???

También lo dijo Martin Fowler.

---
name: metrics-2
layout: false
## Cuatro Métricas Clave

Comparando organizaciones de elite contra las de baja performance:

.image-scaled[![comparing-metrics](comparing-metrics.png)]

???

Acá, el grupo de DevOps Research and Assessments tiene algunos números para mostrarlo.

---
name: proposal
class: center, middle, inverse

## La propuesta de DORA

### Capacidades Técnicas

### Capacidades de Procesos

### Capacidades Culturales

<hr />

<https://dora.dev/devops-capabilities/>

???

_Revisaremos esto directamente en la página junto con los asistentes_

Puntos interesantes:

* Cloud infrastructure: Las organizaciones de elite, cumplen los 5 puntos. Tener una VM en la nube no es estar en la nube.
* Loosely coupled architecture: Conway Law. Real independencia entre los servicios, tiene que ser posible testear y publicarlos independientemente. Twelve-factor app.
* Shifting left on security: Deming: "Cease dependence on inspection to achieve quality. Eliminate the need for inspection on a mass basis by building quality into the product in the first place.". ❌ phased approach.
* Trunk-based development: No es tan literal, los PRs de small batches son considerados trunk-based development.
* Version control: TODO en el control de versiones.
* Streamlining change approval: Change approval boards suelen traer más inestabilidad que estabilidad.

---
name: how-to-implement
## ¿Como lo implementamos?

_"The best strategies for scaling DevOps in organizations focus on structural solutions that build community"_

✅ Comunidades de prácticas

✅ Button-up o grassroots 

✅ POC as a template

✅ POC as a seed

❌ Reorgs (Big bang approach)

❌ Center of excellence

❌* Training centers or dojos

<hr />

<https://dora.dev/devops-capabilities/cultural/devops-culture-transform/>

???

* Training centers or dojos: En algunas organizaciones de alta performance funcionaron, pero son las que dedicaron una cantidad de recursos extremadamente altos en hacerlo muy bien.
* Center of excellence: vs breaking silos y healthy organizational cultures. Experts are able to make recommendations or establish **generic** “best practices”.


---
name: where-to-start
class: inverse
## Pero... ¿por donde empezar?

<br />

### ❌ _Maturity model_

???

A muchas organizaciones les gustan los "modelos de madurez". Tener un roadmap de 3 a 5 años que nos van a llevar al _nirvana_. Esa no es la propuesta de DORA porque cada organización es diferente.

--

<br />

### _Value stream mapping_ / _Process-based constraint approach_ / _DORA capabilities-based approach_

--

<br />

### AKA ¿Cual es mi principal dolor de cabeza? 

???

La propuesta, entonces, es identificar cual de esas capacidades (o falta de ella) es la que más nos está frenando y dedicarle recursos: foco, tiempo, dinero, etc.

Además, iterar de esta manera ayuda a _formar músculo_ porque siempre hay que estar mejorando. Este es un trabajo que no termina nunca.

--
<br />

<hr/>

<br />

<https://dora.dev/quickcheck/>

---
name: everybody
layout: false
class: center, middle, inverse

<!-- ![Out of the Crisis](out-of-the-crisis.png) -->
![Deming](deming.jpg)

_“Put everybody in the company to work to accomplish the transformation. The transformation is everybody's job.”_

― W. Edwards Deming, Out of the Crisis 
