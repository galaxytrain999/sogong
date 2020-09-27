# \<Use Case Diagram\>

![Usecase##2](https://user-images.githubusercontent.com/70693938/94356801-6653dd80-00cd-11eb-82f3-6e1aecc49b45.PNG)


---

# \<Scenario Description\>

**Scenario name** 임산부 배려석에 앉기

**Participating actor** Beacon(임산부A,임산부B)

**Instances** Beacon receiver

**Flow of events** 

1\. Beacon(임산부A)가 지하철 칸 안에 들어가 임산부 배려석에 이미 일반인이 앉아있는 것을 본다.

2\. Beacon(임산부A)가 배려석 가까이 다가가자 배려석에 있는 Beacon receiver가 감지해 배려석에서 빛(Light1)이 나며 소리(sound1)가 나기 시작한다.

3\. 배려석에 앉아있던 일반인은 주위의 시선을 의식해 자리에서 일어난다.

4\. Beacon(임산부A) 가 자리에 착석하고, 무게 감지 센서는 앞의 사람과 무게가 달라진 걸 확인한다.

5\. Beacon receiver의 소리와 빛(LED)은 꺼진다.

6\. 몇 분 후, Beacon(임산부B)가 나타나 Beacon(임산부A)의 좌석 앞에 서서 Beacon receiver가 이를 감지해 빛과 소리를 낸다.

7\. 무게 감지 센서는 같은 무게를 측정하지만, 이미 Beacon(임산부A)가 착석해 있기 때문에 다른 소리(sound2)와 빛(Light2)을 30초동안만 작동시킨다.

8\. Beacon(임산부B)는 다른 임산부 배려석으로 이동한다.

---

# \<Use Case Description\>

**Use case name** 임산부 배려석에 앉기

**Participating actors** Beacon(임산부)이 시작시킨다.<br/>  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Beacon Receiver가 받아 Sound sensor, Light Sensor, Timer, weight sensor와 통신한다.

                     
                       

**Flow of events** 

1\. Beacon(임산부A) 가 임산부 배려석 (Beacon receiver)으로 간다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2\. BeaconSensorSystem은 거리 내에 도달한 Beacon한테 받은 signal을 Beacon receiver에 전달한다.

3\. Beacon receiver는 signal을 받고, 3m이내로 Beacon과 가까워지면 신호를 보낸다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4\. BeaconSensorSystem은 받은 신호를 Sound Sensor와  Light Sensor에게 전달한다.

5\. Sound Sensor는 Sound1, Light Sensor는 Light1을 동작시킨다.

6\. Beacon(임산부A) 가 배려석에 앉는다. 

7\. Weight sensor가 그 전의 무게와 달라졌다는 것을 감지하고 신호를 보낸다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;8\. BeaconSensorSystem이 받은 신호를 Light Sensor와 Sound Sensor에게 전달한다.

9\. Light Sensor와 Sound Sensor는 동작을 중지시킨다.

10\. Beacon(임산부 B)는 Beacon(임산부A)의 배려석으로 다가간다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;11\. BeaconSensorSystem은 거리 내에 도달한 Beacon(임산부B)한테 받은 signal을 Beacon receiver에 전달한다.

12\. Beacon receiver는 signal을 받고, 3m이내로 Beacon(임산부B)와 가까워지면 신호를 보낸다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;13\. BeaconSensorSystem은 받은 신호를 Sound Sensor와 Light Sensor와 Timer에게 전달한다.

14\. Sound Sensor는 Sound2, Light Sensor는 Light2, Timer를 동작 시킨다.

15\. Beacon(임산부B)는 다른 배려석으로 이동한다.

---

**Entry condition** Beacon이 Beacon receiver와 거리내에 접근한다..

---

**Exit conditions** 첫번째 Beacon이 감지될 경우, 무게 변화가 있을 시 센서가 작동을 멈춘다. 

---

**Quality requirements** 두번째 Beacon이 감지될 경우, 센서는 감지 후 30초 동안만 작동된다<br/>
&nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Beacon receiver가 Beacon을 감지하고 센서를 작동시킨다.
                          




---
---


<비콘을 이용한 임산부 배려시스템>


• 사용대상자: 임산부 


• 풀고자 하는 문제: 


- 자리가 비어 있는 경우에도 노약자와 다르게 겉으로 티가 안 나는 임산부들은 지하철을 이용 시, 쉽게 자리를 양보 받지 못함

-	이 시스템을 이용해 일반인이 임산부 배려석에 앉아있을 시, 임산부가 쉽게 양보 받을 수 있게 만들고자 함.



• I/O device


-비콘

	Bluetooth 4.0 에서부터 소개된 핵심 기술이며, 특징은 저전력을 사용한다. 

	비콘은 50미터(m) 범위에서 통신이 가능

	비콘은 사용자 개입 없이 커뮤니케이션이 가능하다는 특징이 있다.




• Functional & nonfunctional

①	국가인증병원에서 주는 비콘을 사용.

②	최대 50m여서 지하철은 매 칸마다 X n칸마다 설치

③	 오차 범위 5cm 이내로 기기의 위치를 파악할 수 있음. (정확성) 

④	임산부가 가지고 있는 비콘과 임산부 배려석이 거리가 3미터 이하로 차이날 때 센서가 반응.

⑤	비콘수신기에서 빛(LED)과 소리가 남. (일반인이 앉아 있으면 남의 시선 의식으로 일어 남.)

⑥	LED와 소리는 30초동안만 남.






| Participant    | Role                                             | Skill                        | Traning needs              |
|----------------|--------------------------------------------------|------------------------------|----------------------------|
| Kim jung uk    | Team Leader<br>API engineer                      | JAVA<br>C<br>PYTHON<br>MYSQL | UML<br>Communication Skill |
| Kim min Hee    | Human factor specialist<br>Developer(programmer) | JAVA<br>C<br>MYSQL           | UML<br>JAVA                |
| Park ji hye    | Technical Writer                                 | JAVA<br>C<br>PYTHON          | UML                        |
| Han seon kyung | Liaison<br>DBA                                   | C<br>JAVA<br>PYTHON<br>MYSQL | UML                        |



