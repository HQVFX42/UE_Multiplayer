# UE_Multiplayer
- steam online subsystem plugin

## Online SubSystem
- Create online subsystem child
  <img src="./Images/Image_01.png" width="100%"/>
	- [MultiplayerSessionsSubsystem.h](./Plugins/MultiplayerSessions/Source/MultiplayerSessions/Public/MultiplayerSessionsSubsystem.h)
	- [MultiplayerSessionsSubsystem.cpp](./Plugins/MultiplayerSessions/Source/MultiplayerSessions/Private/MultiplayerSessionsSubsystem.cpp)
- Accessing the online subsystem   
  	```cpp
	UMultiplayerSessionsSubsystem::UMultiplayerSessionsSubsystem() :
		CreateSessionCompleteDelegate(FOnCreateSessionCompleteDelegate::CreateUObject(this, &ThisClass::OnCreateSessionComplete)),
		FindSessionsCompleteDelegate(FOnFindSessionsCompleteDelegate::CreateUObject(this, &ThisClass::OnFindSessionsComplete)),
		JoinSessionCompleteDelegate(FOnJoinSessionCompleteDelegate::CreateUObject(this, &ThisClass::OnJoinSessionComplete)),
		DestroySessionCompleteDelegate(FOnDestroySessionCompleteDelegate::CreateUObject(this, &ThisClass::OnDestroySessionComplete)),
		StartSessionCompleteDelegate(FOnStartSessionCompleteDelegate::CreateUObject(this, &ThisClass::OnStartSessionComplete))
	{
		IOnlineSubsystem* Subsystem = IOnlineSubsystem::Get();
		if (Subsystem)
		{
			SessionInterface = Subsystem->GetSessionInterface();
		}
	}
  	```
  
## Join session

## Find sessions

## Create session

## Gamemode
