# UE_Multiplayer
- steam online subsystem plugin

## Online SubSystem
- Create online subsystem child
  <img src="./Images/Image_01.png" width="100%"/>
	- [MultiplayerSessionsSubsystem.h](./Plugins/MultiplayerSessions/Source/MultiplayerSessions/Public/MultiplayerSessionsSubsystem.h)
	- [MultiplayerSessionsSubsystem.cpp](./Plugins/MultiplayerSessions/Source/MultiplayerSessions/Private/MultiplayerSessionsSubsystem.cpp)
- Session interface delegates   
	```cpp
	 public:
		UMultiplayerSessionsSubsystem();
	
		//
		// To handle session functionality. The Menu class will call these
		//
		void CreateSession(int32 NumbPublicConnections, FString MatchType);
		void FindSessions(int32 MaxSearchResults);
		void JoinSession(const FOnlineSessionSearchResult& SessionResult);
		void DestroySession();
		void StartSession();
 	```
 	```cpp
	  private:
		IOnlineSessionPtr SessionInterface;
		TSharedPtr<FOnlineSessionSettings> LastSessionSettings;
		TSharedPtr<FOnlineSessionSearch> LastSessionSearch;
	
		//
		// To add to the Online Session Interface delegate list.
		// Bind our MultiplayerSessionSubsystem internal callbacks to these.
		//
		FOnCreateSessionCompleteDelegate CreateSessionCompleteDelegate;
		FDelegateHandle CreateSessionCompleteDelegateHandle;
	
		FOnFindSessionsCompleteDelegate FindSessionsCompleteDelegate;
		FDelegateHandle FindSessionsCompleteDelegateHandle;
	
		FOnJoinSessionCompleteDelegate JoinSessionCompleteDelegate;
		FDelegateHandle JoinSessionCompleteDelegateHandle;
	
		FOnDestroySessionCompleteDelegate DestroySessionCompleteDelegate;
		FDelegateHandle DestroySessionCompleteDelegateHandle;
	
		FOnStartSessionCompleteDelegate StartSessionCompleteDelegate;
		FDelegateHandle StartSessionCompleteDelegateHandle;
  	```
 
  
## Join session

## Find sessions

## Create session

## Gamemode
