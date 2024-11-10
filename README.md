# GDSerialRead

A plugin for serial data reading in Godot Engine 4.3, aimed at bridging communication between devices like Arduino and Godot to create dynamic interactions in games and applications.

## Table of Contents
- [About the Project](#about-the-project)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [License](#license)

## About the Project

`GDSerialRead` offers a straightforward solution for reading serial data directly in Godot, making it ideal for integrating external devices like Arduino with the engine. This project was initially developed to simulate and capture data from an Arduino Esplora in a Linux environment, enabling real-world hardware and software interactions in a game environment.

## Requirements

- [**Godot Engine - .NET**](https://godotengine.org/download/windows/) 4.3 or higher.
- [SDK do .NET 8](https://dotnet.microsoft.com/pt-br/download) version usade in project.
- Build System.IO.Ports in project paste: ```dotnet add package System.IO.Ports```

  
## Installation


### 1. In the project editor in godot initialize the environment for C# following the path below:
``` 
Project --> Tools --> C# --> Creat C# solution 
```
<div align="center">
    <img src="https://private-user-images.githubusercontent.com/159396360/384693882-78e9ca9d-bc24-4b9a-aede-c418a9fbdb5f.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzEyNDY4NzQsIm5iZiI6MTczMTI0NjU3NCwicGF0aCI6Ii8xNTkzOTYzNjAvMzg0NjkzODgyLTc4ZTljYTlkLWJjMjQtNGI5YS1hZWRlLWM0MThhOWZiZGI1Zi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExMFQxMzQ5MzRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04MDU0ZDk4ZDdmMTVjNzk2NjYyNGMyODU3NzBkMTlmOTJkMThmOGI1MTdiNzgxNTQxZWZlNjc2ZWM3ZTkzN2I4JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.DWCmGkb5OtAJezL3sTpZroVBL4cwa3qzKv3unH38-nM" alt="Descrição da imagem" width="800"/> 
<div/>

### 2. After initializing the environment, open a terminal with the path to the main folder of the Godot project.

<div align="center">
    <img src="https://private-user-images.githubusercontent.com/159396360/384693883-c9d819ce-3819-4b6d-a500-26ea5f6baa0c.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzEyNDY4NzQsIm5iZiI6MTczMTI0NjU3NCwicGF0aCI6Ii8xNTkzOTYzNjAvMzg0NjkzODgzLWM5ZDgxOWNlLTM4MTktNGI2ZC1hNTAwLTI2ZWE1ZjZiYWEwYy5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExMFQxMzQ5MzRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1jYmY1N2IyY2IxMmU1NjczMjM0NDFhYzk5NDRhYjFkY2M1ZjNmNTQyMzcyMTgyZmVkOTIyNGJkYWJiMGFiMTgyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.dV5-ncwjBg7SDaNXn-17THpTy7tffTc4gnTJR4cmY9A" alt="Descrição da imagem" width="800"/>
<div/>

### 3. Clone the main branch of the repository into the project folder 
``` 
git clone https://github.com/NicolasRaf/GDSerialRead.git
```
<div align="center">
    <img src="https://private-user-images.githubusercontent.com/159396360/384693874-3985290b-4434-43ef-9c40-6758bba95328.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzEyNDc1ODIsIm5iZiI6MTczMTI0NzI4MiwicGF0aCI6Ii8xNTkzOTYzNjAvMzg0NjkzODc0LTM5ODUyOTBiLTQ0MzQtNDNlZi05YzQwLTY3NThiYmE5NTMyOC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExMFQxNDAxMjJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1mMGNkYTNhZDNkNDI4NDQxN2FjYzJiZDMwOGZhN2I1MjgwMWZiNTQ0MTZkNDE3N2IzOGU0ZGE1Mjg0OGNmZWQwJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.5EHYW0y6fNv9tFjKQu3mDEKRjqcB0IA_XP2fA83bW84" alt="Descrição da imagem" width="800"/>
<div/>

### 4. Still in the terminal, install the “System.IO.Ports” package in your project's main folder
```
dotnet add package System.IO.Ports
````
<div align="center">
    <img src="https://private-user-images.githubusercontent.com/159396360/384693877-d60e16aa-8167-4ba4-aef5-bdc7cdecf5ea.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzEyNDY4NzQsIm5iZiI6MTczMTI0NjU3NCwicGF0aCI6Ii8xNTkzOTYzNjAvMzg0NjkzODc3LWQ2MGUxNmFhLTgxNjctNGJhNC1hZWY1LWJkYzdjZGVjZjVlYS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExMFQxMzQ5MzRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT02OGJhNzNhMGIyYWExZjM3ZTg1NmE4YmViNDMxZDM4NmNhZWNkYWQzZGQwOWRjZDk4OTA3NzMxMzM4OTFjNzUxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.22JdIqKNGMnJLSUmMhKVIdUos1qYyeYEdZ5DVuaGXQw" alt="Descrição da imagem" width="800"/>
<div/>


### 5. Now inside Godot open the scene called “DataReceiver.tscn” and assign the script “DataReceiver.gd” to the node.

<div align="center">
    <img src="https://private-user-images.githubusercontent.com/159396360/384694687-4394e286-df14-4a34-b18a-42be40294fc5.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzEyNDc0NjAsIm5iZiI6MTczMTI0NzE2MCwicGF0aCI6Ii8xNTkzOTYzNjAvMzg0Njk0Njg3LTQzOTRlMjg2LWRmMTQtNGEzNC1iMThhLTQyYmU0MDI5NGZjNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExMFQxMzU5MjBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04NmQzY2Q5NTc5ZDZlNzczNmRjNGZjZDBiNmQ0MGU4M2IwYjViZWYzNTVkNzhlZWQ1MDdmZjg5MzI3MjU3ZTVhJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.KmAbZmpQGZwR2-csSi5NjzOalCNMqxZVJOvLArHkrGU" alt="Descrição da imagem" width="800"/>
<div/>

### 6. After that, the program is up and running and you can receive and manipulate data from the “DataReciever.gd” node.

<div align="center">
    <img src="https://private-user-images.githubusercontent.com/159396360/384693879-06e1b34b-3842-48a5-bd66-67b01dd52315.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzEyNDc0NjAsIm5iZiI6MTczMTI0NzE2MCwicGF0aCI6Ii8xNTkzOTYzNjAvMzg0NjkzODc5LTA2ZTFiMzRiLTM4NDItNDhhNS1iZDY2LTY3YjAxZGQ1MjMxNS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExMFQxMzU5MjBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wZTM3MTZhODk5NzUxZWUwMzNmY2E2MjI3ZTkyMGY4YWVmNWFmMTc0ZTYyZWQ0MmExMTk0ZDkwMDU1NzQ0MTQzJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.oTtUQuJW6Wyi80BqF7j4jVXItpZnPTMKZpgq7a7Jr_4" alt="Descrição da imagem" width="800"/>
<div/>
