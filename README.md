//Atividade-Uninter
//TRABALHO PRÁTICO - ANÁLISE E MODELAGEM DE SISTEMAS  
//Aluno: Larissa da Silva Machado 
//Curso: Análise e Desenvolvimento de Sistemas 
//Data: 17/05/2025 
//Empresa: Berg Work Money - Proprietária: Mariane Bergamini

//Meu código para o Diagrama de caso de Uso, feito no PlantUML

@startuml
title Casos de Uso - Sistema de Automação da Berg Work Money

actor "Funcionário" as Func
actor "RH" as RH
actor "Gestora (Mariane)" as Gestora
actor "Suporte Técnico" as Suporte

rectangle "Sistema de Automação" {
  
  usecase "Abrir porta com comando de voz" as UC1
  usecase "Abrir porta com reconhecimento facial" as UC2
  usecase "Controle de Luz (voz ou movimento)" as UC3
  usecase "Controle de Ar-Condicionado\n(desligar aos 17°C)" as UC4
  usecase "Registrar Acesso" as UC5
  usecase "Capturar Imagem de Segurança" as UC6
  usecase "Solicitar Suporte Técnico" as UC7
  
  UC3 .> UC7 : <<extend>>
}

Func --> UC1
Func --> UC3
Func --> UC4
Func --> UC5

RH --> UC1
RH --> UC2
RH --> UC5

Gestora --> UC1
Gestora --> UC2
Gestora --> UC3
Gestora --> UC4
Gestora --> UC5
Gestora --> UC6

Suporte <-- UC7

@enduml
