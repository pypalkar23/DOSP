# DOSP Bitcoin Miner #

## Project Members ##
* Mandar Palkar (UFID: 2140-6740)
* Siddhi Wadgaonkar (UFID: 9544-2212)

## Requirements: ##
The project was tested with
* dotnet SDK - version 5.0.401
* Akka - version 1.4.25
* Akka.FSharp - version 1.4.25
* Akka.Remote - version 1.4.25


## Steps to run: ##
Run following commands in your console.

### To Run 'Server'###
* ``cd Server``
* ``dotnet run {k}`` or ``dotnet run`` 
  Where *k* is the number of zeros coins' hash should start with . default value of k is 4 if not supplied while running the program.

### To Run 'RemoteWorker' ###
* ``cd RemoteWorker``
* ``dotnet run {ip_address}`` or ``dotnet run``
    default value is of ip_address is ``0.0.0.0``

### What does the Program performs: ###
- The server processes total job size which is 'k' (input given to the server) multiplied by ``100000000``. for e.g for the input of k = 5 the total job size will be ``500000000``.
-  The server processes the job in the batches of ``2000000``.
-  If remote worker joins it assigns next batch which is yet to be processed for minting coins.
-  Coins that are minted by both (Server and RemoteWorker) are displayed on Server's console (Through PrinterActor)
-  Whenever RemoteWorker finishes processing of the batch assigned to it. It notifies the Server.
-  If there are more batches that are yet to be processed on the server, then the Server assigns the next batch inline to the remote worker.
- When there are no more batches to be processed. Server sends ``shutdown`` signal to RemoteWorker(if there is one) asking it to terminate and then terminate itself.


### Program Results ###
**Sample Coins Mined:**    
6139 mandar.palkar396188865 0000d2baef3ecf2e1bb9ec2d258f3820820fb622927018d5afafe153ae15b4d2
6140 mandar.palkar396283901 0000a3ad93ee38cb61b4ec6aca99c0558d697fee4581ff0c1f09f6dc9e7d938c
6141 mandar.palkar396322433 000094f6ec225954d98f25c01337afcab87a3fced067c93e1112851a52e478aa
6142 mandar.palkar396360135 0000aefe8dba8a8db142ea25f9cf11e3680e4cd897adad3959668dc8c4d8faca
6143 mandar.palkar396368905 0000ea2dd53277099c04a6b35042891d68c5136ecad8db923dda932540cfff47
6144 mandar.palkar396420312 0000bc2345b16acd3b7d907fecf592553b334b0e338e225260d4c5a417c136b6
6145 mandar.palkar396428830 0000ca65076dda0c6dbf9e747eb9488dff5fc5ac414a4165f7bb57ee8f88a855
6146 mandar.palkar396458286 000027cc82b8f1a82f9b2c77d92e867e353f4f30e8c5514f79b3612990f16e22
6147 mandar.palkar396596941 000086850dcd3c19923ddeee123cea17edae967cdeb8ca86ac7d1863ce6cf138
6148 mandar.palkar396629713 0000537c2bced327afca3525c23265b97b9c3044e9355d120cc975cf2afbf542
6149 mandar.palkar396655883 00002ba3384fccb1dc569d536b06e3d68461ecb2fbfdc427d7031d20a32705e3
6150 mandar.palkar396669781 000064d974d498de1bffcaedc1d6d8921e92278152b57ff724ed69b3301644f0
6151 mandar.palkar396728552 0000b17122c80e5819ab98e955601dae9c41696c4c67d75df48ec98a216e62df
6152 mandar.palkar396728981 00007080e002b317cbb439d709f577e3efe40e3c581302713472d7bc4d310f76
6153 mandar.palkar396755691 00006300f8472eae502f0e9257d3d71e87fa7812bf7ee6bffdb186fc80ca64e8
6154 mandar.palkar396845344 0000eb7961b0e95f4d196e25bb4c201ebddf40f3f5a59e7851ac9bf3eed29664
6155 mandar.palkar396855447 0000f4e6989e2476e7410a724d72a7fb9813cea8b94da9877e49c5fa5b7a2bf0
6156 mandar.palkar396861549 000069213a711e079004cbbfd63aa0b4f597708a1ffc8fbd647426d884b9b250
6157 mandar.palkar396948176 0000ed7d392ce0c844c66da37cb21777d12218d9d8e884089f6449dfe0a0a34f
6158 mandar.palkar396994009 000024e318355e39dd6f74dfc494097f035ef8a8db49e41cab5b130cfa229ad8
6159 mandar.palkar397062419 0000e68b27f7383d9d80471cd1847a1be357077c3c30f75f9886031e8eae0ddc
6160 mandar.palkar397089189 0000b350d237dc2640b2ce8646f166a169220a8a27a6ef8f5babf5bd7b72f7ea
6161 mandar.palkar397173344 0000538f44115a32305cfa9f94d3b99c1893183a7f02311e14b4a4ef832eae46
6162 mandar.palkar397607883 000097e905a82d8bb3436781080361afabbc02651889c2dafa502b46b7c1a03a
6163 mandar.palkar397630247 000037941fbb4d60b78b97ec7e5975939e6f677d6d1becdec2a8eb6a2eb82109
6164 mandar.palkar397719433 0000cc0e8fad2bac08e8c7c1f46288ef2a9a278aac1d42c1bc8e401ce7761f78
6165 mandar.palkar397808909 00003837684d6a6cd6955a0fe3ed7ca95650a942b3691259f009149e3b988842
6166 mandar.palkar397827544 0000e11abbb6d2532380cb0da55748afac95146b3bc3aba4560e7d5a66aec69d
6167 mandar.palkar397836838 00003d4cf1e50878981b60bba80af474f2e0315616f22ef3b1c9093e293dee32
6168 mandar.palkar397937952 000002e7fe9a5c3813dbfc85a03fa79b57e592275616cfccaa60205ff27cdde5
6169 mandar.palkar397977213 00001dfc26728862e28d1ebba1711c7dc5d87664be921dc3d3da4001ba3a9de3
6170 mandar.palkar397997374 00003972357932e329e14a5433c9859600f9e8223af0157fb377337c53905ce1


#### Benchmarks For 4 Coins:####
**Results**:
- Coins Mined (4 zeros): 6170

**Server Machine Configuration:**
- Processor: Intel Core i7-5500U CPU@2.40 Ghz
- Cores :4
- Actors : 1000 
- CPU Time: 2392200 ms
- Absolute Time: 880255 ms

**Remote Machine Configuration:**
- Processor: Intel Core i3-5005U CPU @ 2.00GHz
- Cores: 4
- Actors: 1000
- CPU Time: 2042480 ms
- Absolute Time: 850817 ms

**Largest Coin Found**
1 mandar.palkar573263448 000000061a2eb7de66acb48721f1bb2338d87793b36523182bbb691a389602e7 r







