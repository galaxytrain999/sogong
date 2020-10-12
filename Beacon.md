# \<Sequence Diagram\>   

1.Send weight 담당자 : 한선경

![시퀀스 sendweight](https://user-images.githubusercontent.com/70693938/95677741-92f61200-0c02-11eb-964c-30df890f6dd1.png)


2.Turn off light 담당자 : 한선경, 박지혜

![시퀀스 turn off light](https://user-images.githubusercontent.com/70693938/95677742-94273f00-0c02-11eb-8500-fadf96fd0ac3.png)

3.Turn on sound 담당자 : 박지혜

![시퀀스 turn on sound](https://user-images.githubusercontent.com/70693938/95677744-94273f00-0c02-11eb-9038-d05470796a5d.png)

# \<Class Diagram\>
담당자 : 김정욱, 한선경

![클래스2](https://user-images.githubusercontent.com/70693938/95739647-1d537a00-0cc6-11eb-8ea9-846194474a95.png)


# \<Obeject Diagram\>   
담당자 : 김민희

![객체](https://user-images.githubusercontent.com/70693938/95677746-94bfd580-0c02-11eb-999f-d89ced0c7328.png)

---

# \<Use Case Diagram\>   담당자 : 김정욱 ,박지혜, 한선경


![usecase#4](https://user-images.githubusercontent.com/70693938/95335220-19041700-08ea-11eb-9f6d-b4322559d0a4.png)



---

# <경쟁사와의 차별 점> 

경쟁사

-임산부가 거리 내에 오면 멘트와 함께 빛이 30초동안만 남. 

-임산부가 앉았는지 못 앉았는지 알 수 없음.

-임산부가 앉아있는 상태에서 다른 임산부가 왔을 때 반응이 없음.  


9조

-임산부가 거리내에 오면 앉아있는 사람이 일반인인지 임산부인지에 따라 효과가 다름.

-무게감지를 이용해 앉아있던 사람과 임산부가 앉은 걸 구별할 수 있음. 

-임산부가 앉아있는 상태에서 새로운 임산부가 오면 다른 빛과 소리를 30초동안 작동하므로 서로 알 수 있다.

---

# \<Usecase Description 1 \>

**Use case name**       Measure Distance

**Participating Sender**    BeaconSender(임산부A,임산부B)<br/>

 &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Beacon Receiver
 
**Flow of events** 

1\. Beacon(임산부A) 가 임산부 배려석 (Beacon receiver)으로 간다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2\. BeaconSenderSystem은 거리 내에 도달한 BeaconSender(임산부A)한테 받은 signal을 Beacon Receiver에</br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;전달한다.

3\. BeaconSender(임산부A) 은 Measure Distance를 동작을 하고, BeaconSender(임산부A) 과 Beacon Receiver사이의 거리가 3m이내로 도달하면 신호를 보낸다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4\. BeaconSenderSystem은 신호를 Beacon Receiver에 전달한다. 

**Entry condition** Beacon이 Beacon receiver와 거리내에 접근한다.

**Exit conditions** BeaconSender가 Beacon Reciver에 시그널을 보낸다

**Quality requirements**  Beacon Receiver가 Beacon을 감지하고 센서를 작동시킨다.

---

# \<Usecase Description 2 \>

**Use case name**      Send weight

**Participating Sender**     Beacon Receiver<br/>

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Weight Sensor
 
**Flow of events** 

1\. Timer는 set timer를 수행한다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2\. BeaconReceiverSystem은 weight Sensor에 Timer의 신호를 보낸다..

3\. Weight Sensor는 무게를 측정하고, 변화가 있을 시 신호를 보낸다. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4\. BeaconReceiverSystem은 받은 신호를	Speaker와Lamp에 전달한다. 

**Entry condition** Beacon이 Beacon Receiver와 거리내에 접근한다.

**Exit conditions** 

**Quality requirements**  Beacon Receiver가 Beacon을 감지하고 센서를 작동시킨다

---

# \<Usecase Description 3 \>

**Use case name**      Turn On Sound2

**Participating Sender**    Beacon Receiver<br/>

 &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Weight Sensor
 
**Flow of events** 

1\. BeaconSender(임산부A)가앉은 상태에서 BeaconReceiver는 BeaconSender(임산부B)에게 Measure Distance를 받았으므로 신호를 보낸다


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2\. BeaconReceiverSystem은 Speaker에 신호를 전달 한다.

3\. Speaker는 Sound2를 동작 시킨다.  


**Entry condition** Beacon이 Beacon Receiver와 거리내에 접근한다.

**Exit conditions** 30초가 지난다

**Quality requirements**  Beacon Receiver가 Beacon을 감지하고 센서를 작동시킨다

---                         

# \<Usecase Description 4 \>

**Use case name**     Turn off Light

**Participating Sender**     Lamp<br/>

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Weight Sensor
 
**Flow of events** 

1\. Light1 또는 2가 동작하고 있다.


2\. Weight Sensor가 무게변화를 감지하여 신호를 보낸다.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3\. BeaconReceiverSystem은 신호를 받아 Lamp에 전달해준다.

4.1 Light1일 때는 Turn Off Light를 동작한다.

4.2 Light2일때는 무게와 상관없이 Blink light2를 동작한 뒤 30초 뒤에 Turn off Light를 동작 시킨다

**Entry condition** Beacon이 Beacon Receiver와 거리내에 접근한다.

**Exit conditions** 첫번째 Beacon이 감지될 경우, 무게 변화가 있을 시 센서가 작동을 멈춘다. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;두번째 Beacon이 감지될 경우, 센서는 감지 후 30초 동안    만 작동된다.


**Quality requirements**  Beacon Receiver가 Beacon을 감지하고 센서를 작동시킨다

---                         

# \<Scenario Description 1 \>

**Scenario name**     일반인이 앉아있는 경우

**Participating Sender**    BeaconSender (임산부A)

**Instances** 			Beacon Receiver

**Flow of events**    1. BeaconSender (임산부A)가 지하철 칸 안에 들어가 임산부 배려석에 이미 일반인이 앉아있는 것을 본다.</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. BeaconSender (임산부A)가 배려석 가까이 다가가자 배려석에 있는 Beacon Receiver가 감지해 배려석에서  빛(Light1)이 나며 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;소리(sound1)가 나기 시작한다.                         
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3. 배려석에 앉아있던 일반인은 주위의 시선을 의식해 자리에서 일어난다.</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4. BeaconSender (임산부A) 가 자리에 착석하고, 무게 감지 센서는 앞의 사람과 무게가 달라진 걸 확인한다.</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;5. Beacon Receiver의 소리와 빛(LED)은 꺼진다</br>



---
# \<Scenario Description 2 \>

**Scenario name**     임산부가 앉아있는 경우

**Participating Sender**    BeaconSender(임산부A, 임산부B)

**Instances** 			Beacon Receiver

**Flow of events**   1. BeaconSender (임산부B)가 나타나 BeaconSender (임산부A)의 좌석 앞에 서서 Beacon Receiver가 이를 감지해 빛과 소리를 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;낸다.</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. 무게 감지 센서는 같은 무게를 측정하지만, 이미 BeaconSender (임산부A)가 착석해 있기 때문에 다른 소리(sound2)와 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;빛(Light2)을 30초동안만 작동시킨다.</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3. BeaconSender (임산부B)는 다른 임산부 배려석으로 이동한다.</br>
                  


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



