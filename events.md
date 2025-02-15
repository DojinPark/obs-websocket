# Events

## Events Table of Contents

- [General Events](#general-events)
  - [ExitStarted](#exitstarted)
  - [VendorEvent](#vendorevent)
  - [CustomEvent](#customevent)
- [Config Events](#config-events)
  - [CurrentSceneCollectionChanging](#currentscenecollectionchanging)
  - [CurrentSceneCollectionChanged](#currentscenecollectionchanged)
  - [SceneCollectionListChanged](#scenecollectionlistchanged)
  - [CurrentProfileChanging](#currentprofilechanging)
  - [CurrentProfileChanged](#currentprofilechanged)
  - [ProfileListChanged](#profilelistchanged)
- [Scenes Events](#scenes-events)
  - [SceneCreated](#scenecreated)
  - [SceneRemoved](#sceneremoved)
  - [SceneNameChanged](#scenenamechanged)
  - [CurrentProgramSceneChanged](#currentprogramscenechanged)
  - [CurrentPreviewSceneChanged](#currentpreviewscenechanged)
  - [SceneListChanged](#scenelistchanged)
- [Inputs Events](#inputs-events)
  - [InputCreated](#inputcreated)
  - [InputRemoved](#inputremoved)
  - [InputNameChanged](#inputnamechanged)
  - [InputSettingsChanged](#inputsettingschanged)
  - [InputActiveStateChanged](#inputactivestatechanged)
  - [InputShowStateChanged](#inputshowstatechanged)
  - [InputMuteStateChanged](#inputmutestatechanged)
  - [InputVolumeChanged](#inputvolumechanged)
  - [InputAudioBalanceChanged](#inputaudiobalancechanged)
  - [InputAudioSyncOffsetChanged](#inputaudiosyncoffsetchanged)
  - [InputAudioTracksChanged](#inputaudiotrackschanged)
  - [InputAudioMonitorTypeChanged](#inputaudiomonitortypechanged)
  - [InputVolumeMeters](#inputvolumemeters)
- [Transitions Events](#transitions-events)
  - [CurrentSceneTransitionChanged](#currentscenetransitionchanged)
  - [CurrentSceneTransitionDurationChanged](#currentscenetransitiondurationchanged)
  - [SceneTransitionStarted](#scenetransitionstarted)
  - [SceneTransitionEnded](#scenetransitionended)
  - [SceneTransitionVideoEnded](#scenetransitionvideoended)
- [Filters Events](#filters-events)
  - [SourceFilterListReindexed](#sourcefilterlistreindexed)
  - [SourceFilterCreated](#sourcefiltercreated)
  - [SourceFilterRemoved](#sourcefilterremoved)
  - [SourceFilterNameChanged](#sourcefilternamechanged)
  - [SourceFilterSettingsChanged](#sourcefiltersettingschanged)
  - [SourceFilterEnableStateChanged](#sourcefilterenablestatechanged)
- [Scene Items Events](#scene-items-events)
  - [SceneItemCreated](#sceneitemcreated)
  - [SceneItemRemoved](#sceneitemremoved)
  - [SceneItemListReindexed](#sceneitemlistreindexed)
  - [SceneItemEnableStateChanged](#sceneitemenablestatechanged)
  - [SceneItemLockStateChanged](#sceneitemlockstatechanged)
  - [SceneItemSelected](#sceneitemselected)
  - [SceneItemTransformChanged](#sceneitemtransformchanged)
- [Outputs Events](#outputs-events)
  - [StreamStateChanged](#streamstatechanged)
  - [RecordStateChanged](#recordstatechanged)
  - [RecordFileChanged](#recordfilechanged)
  - [ReplayBufferStateChanged](#replaybufferstatechanged)
  - [VirtualcamStateChanged](#virtualcamstatechanged)
  - [ReplayBufferSaved](#replaybuffersaved)
- [Media Inputs Events](#media-inputs-events)
  - [MediaInputPlaybackStarted](#mediainputplaybackstarted)
  - [MediaInputPlaybackEnded](#mediainputplaybackended)
  - [MediaInputActionTriggered](#mediainputactiontriggered)
- [Ui Events](#ui-events)
  - [StudioModeStateChanged](#studiomodestatechanged)
  - [ScreenshotSaved](#screenshotsaved)

## General Events

### ExitStarted

OBS has begun the shutdown process.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

---

### VendorEvent

An event has been emitted from a vendor.

A vendor is a unique name registered by a third-party plugin or script, which allows for custom requests and events to be added to obs-websocket.
If a plugin or script implements vendor requests or events, documentation is expected to be provided with them.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| vendorName | String | Name of the vendor emitting the event |
| eventType | String | Vendor-provided event typedef |
| eventData | Object | Vendor-provided event data. {} if event does not provide any data |

---

### CustomEvent

Custom event emitted by `BroadcastCustomEvent`.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| eventData | Object | Custom event data |

## Config Events

### CurrentSceneCollectionChanging

The current scene collection has begun changing.

Note: We recommend using this event to trigger a pause of all polling requests, as performing any requests during a
scene collection change is considered undefined behavior and can cause crashes!

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneCollectionName | String | Name of the current scene collection |

---

### CurrentSceneCollectionChanged

The current scene collection has changed.

Note: If polling has been paused during `CurrentSceneCollectionChanging`, this is the que to restart polling.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneCollectionName | String | Name of the new scene collection |

---

### SceneCollectionListChanged

The scene collection list has changed.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneCollections | Array&lt;String&gt; | Updated list of scene collections |

---

### CurrentProfileChanging

The current profile has begun changing.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| profileName | String | Name of the current profile |

---

### CurrentProfileChanged

The current profile has changed.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| profileName | String | Name of the new profile |

---

### ProfileListChanged

The profile list has changed.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| profiles | Array&lt;String&gt; | Updated list of profiles |

## Scenes Events

### SceneCreated

A new scene has been created.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the new scene |
| sceneUuid | String | UUID of the new scene |
| isGroup | Boolean | Whether the new scene is a group |

---

### SceneRemoved

A scene has been removed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the removed scene |
| sceneUuid | String | UUID of the removed scene |
| isGroup | Boolean | Whether the scene was a group |

---

### SceneNameChanged

The name of a scene has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneUuid | String | UUID of the scene |
| oldSceneName | String | Old name of the scene |
| sceneName | String | New name of the scene |

---

### CurrentProgramSceneChanged

The current program scene has changed.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene that was switched to |
| sceneUuid | String | UUID of the scene that was switched to |

---

### CurrentPreviewSceneChanged

The current preview scene has changed.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene that was switched to |
| sceneUuid | String | UUID of the scene that was switched to |

---

### SceneListChanged

The list of scenes has changed.

TODO: Make OBS fire this event when scenes are reordered.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| scenes | Array&lt;Object&gt; | Updated array of scenes |

## Inputs Events

### InputCreated

An input has been created.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputKind | String | The kind of the input |
| unversionedInputKind | String | The unversioned kind of input (aka no `_v2` stuff) |
| inputKindCaps | Number | Bitflag value for the caps that an input supports. See obs_source_info.output_flags in the libobs docs |
| inputSettings | Object | The settings configured to the input when it was created |
| defaultInputSettings | Object | The default settings for the input |

---

### InputRemoved

An input has been removed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |

---

### InputNameChanged

The name of an input has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputUuid | String | UUID of the input |
| oldInputName | String | Old name of the input |
| inputName | String | New name of the input |

---

### InputSettingsChanged

An input's settings have changed (been updated).

Note: On some inputs, changing values in the properties dialog will cause an immediate update. Pressing the "Cancel" button will revert the settings, resulting in another event being fired.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.4.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputSettings | Object | New settings object of the input |

---

### InputActiveStateChanged

An input's active state has changed.

When an input is active, it means it's being shown by the program feed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| videoActive | Boolean | Whether the input is active |

---

### InputShowStateChanged

An input's show state has changed.

When an input is showing, it means it's being shown by the preview or a dialog.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| videoShowing | Boolean | Whether the input is showing |

---

### InputMuteStateChanged

An input's mute state has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputMuted | Boolean | Whether the input is muted |

---

### InputVolumeChanged

An input's volume level has changed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputVolumeMul | Number | New volume level multiplier |
| inputVolumeDb | Number | New volume level in dB |

---

### InputAudioBalanceChanged

The audio balance value of an input has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputAudioBalance | Number | New audio balance value of the input |

---

### InputAudioSyncOffsetChanged

The sync offset of an input has changed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputAudioSyncOffset | Number | New sync offset in milliseconds |

---

### InputAudioTracksChanged

The audio tracks of an input have changed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| inputAudioTracks | Object | Object of audio tracks along with their associated enable states |

---

### InputAudioMonitorTypeChanged

The monitor type of an input has changed.

Available types are:

- `OBS_MONITORING_TYPE_NONE`
- `OBS_MONITORING_TYPE_MONITOR_ONLY`
- `OBS_MONITORING_TYPE_MONITOR_AND_OUTPUT`

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| monitorType | String | New monitor type of the input |

---

### InputVolumeMeters

A high-volume event providing volume levels of all active inputs every 50 milliseconds.

- Complexity Rating: `4/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputs | Array&lt;Object&gt; | Array of active inputs with their associated volume levels |

## Transitions Events

### CurrentSceneTransitionChanged

The current scene transition has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| transitionName | String | Name of the new transition |
| transitionUuid | String | UUID of the new transition |

---

### CurrentSceneTransitionDurationChanged

The current scene transition duration has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| transitionDuration | Number | Transition duration in milliseconds |

---

### SceneTransitionStarted

A scene transition has started.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| transitionName | String | Scene transition name |
| transitionUuid | String | Scene transition UUID |

---

### SceneTransitionEnded

A scene transition has completed fully.

Note: Does not appear to trigger when the transition is interrupted by the user.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| transitionName | String | Scene transition name |
| transitionUuid | String | Scene transition UUID |

---

### SceneTransitionVideoEnded

A scene transition's video has completed fully.

Useful for stinger transitions to tell when the video *actually* ends.
`SceneTransitionEnded` only signifies the cut point, not the completion of transition playback.

Note: Appears to be called by every transition, regardless of relevance.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| transitionName | String | Scene transition name |
| transitionUuid | String | Scene transition UUID |

## Filters Events

### SourceFilterListReindexed

A source's filter list has been reindexed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sourceName | String | Name of the source |
| filters | Array&lt;Object&gt; | Array of filter objects |

---

### SourceFilterCreated

A filter has been added to a source.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sourceName | String | Name of the source the filter was added to |
| filterName | String | Name of the filter |
| filterKind | String | The kind of the filter |
| filterIndex | Number | Index position of the filter |
| filterSettings | Object | The settings configured to the filter when it was created |
| defaultFilterSettings | Object | The default settings for the filter |

---

### SourceFilterRemoved

A filter has been removed from a source.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sourceName | String | Name of the source the filter was on |
| filterName | String | Name of the filter |

---

### SourceFilterNameChanged

The name of a source filter has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sourceName | String | The source the filter is on |
| oldFilterName | String | Old name of the filter |
| filterName | String | New name of the filter |

---

### SourceFilterSettingsChanged

An source filter's settings have changed (been updated).

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.4.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sourceName | String | Name of the source the filter is on |
| filterName | String | Name of the filter |
| filterSettings | Object | New settings object of the filter |

---

### SourceFilterEnableStateChanged

A source filter's enable state has changed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sourceName | String | Name of the source the filter is on |
| filterName | String | Name of the filter |
| filterEnabled | Boolean | Whether the filter is enabled |

## Scene Items Events

### SceneItemCreated

A scene item has been created.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene the item was added to |
| sceneUuid | String | UUID of the scene the item was added to |
| sourceName | String | Name of the underlying source (input/scene) |
| sourceUuid | String | UUID of the underlying source (input/scene) |
| sceneItemId | Number | Numeric ID of the scene item |
| sceneItemIndex | Number | Index position of the item |

---

### SceneItemRemoved

A scene item has been removed.

This event is not emitted when the scene the item is in is removed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene the item was removed from |
| sceneUuid | String | UUID of the scene the item was removed from |
| sourceName | String | Name of the underlying source (input/scene) |
| sourceUuid | String | UUID of the underlying source (input/scene) |
| sceneItemId | Number | Numeric ID of the scene item |

---

### SceneItemListReindexed

A scene's item list has been reindexed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene |
| sceneUuid | String | UUID of the scene |
| sceneItems | Array&lt;Object&gt; | Array of scene item objects |

---

### SceneItemEnableStateChanged

A scene item's enable state has changed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene the item is in |
| sceneUuid | String | UUID of the scene the item is in |
| sceneItemId | Number | Numeric ID of the scene item |
| sceneItemEnabled | Boolean | Whether the scene item is enabled (visible) |

---

### SceneItemLockStateChanged

A scene item's lock state has changed.

- Complexity Rating: `3/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene the item is in |
| sceneUuid | String | UUID of the scene the item is in |
| sceneItemId | Number | Numeric ID of the scene item |
| sceneItemLocked | Boolean | Whether the scene item is locked |

---

### SceneItemSelected

A scene item has been selected in the Ui.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | Name of the scene the item is in |
| sceneUuid | String | UUID of the scene the item is in |
| sceneItemId | Number | Numeric ID of the scene item |

---

### SceneItemTransformChanged

The transform/crop of a scene item has changed.

- Complexity Rating: `4/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| sceneName | String | The name of the scene the item is in |
| sceneUuid | String | The UUID of the scene the item is in |
| sceneItemId | Number | Numeric ID of the scene item |
| sceneItemTransform | Object | New transform/crop info of the scene item |

## Outputs Events

### StreamStateChanged

The state of the stream output has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| outputActive | Boolean | Whether the output is active |
| outputState | String | The specific state of the output |

---

### RecordStateChanged

The state of the record output has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| outputActive | Boolean | Whether the output is active |
| outputState | String | The specific state of the output |
| outputPath | String | File name for the saved recording, if record stopped. `null` otherwise |

---

### RecordFileChanged

The record output has started writing to a new file. For example, when a file split happens.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.5.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| newOutputPath | String | File name that the output has begun writing to |

---

### ReplayBufferStateChanged

The state of the replay buffer output has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| outputActive | Boolean | Whether the output is active |
| outputState | String | The specific state of the output |

---

### VirtualcamStateChanged

The state of the virtualcam output has changed.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| outputActive | Boolean | Whether the output is active |
| outputState | String | The specific state of the output |

---

### ReplayBufferSaved

The replay buffer has been saved.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| savedReplayPath | String | Path of the saved replay file |

## Media Inputs Events

### MediaInputPlaybackStarted

A media input has started playing.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |

---

### MediaInputPlaybackEnded

A media input has finished playing.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |

---

### MediaInputActionTriggered

An action has been performed on an input.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| inputName | String | Name of the input |
| inputUuid | String | UUID of the input |
| mediaAction | String | Action performed on the input. See `ObsMediaInputAction` enum |

## Ui Events

### StudioModeStateChanged

Studio mode has been enabled or disabled.

- Complexity Rating: `1/5`
- Latest Supported RPC Version: `1`
- Added in v5.0.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| studioModeEnabled | Boolean | True == Enabled, False == Disabled |

---

### ScreenshotSaved

A screenshot has been saved.

Note: Triggered for the screenshot feature available in `Settings -> Hotkeys -> Screenshot Output` ONLY.
Applications using `Get/SaveSourceScreenshot` should implement a `CustomEvent` if this kind of inter-client
communication is desired.

- Complexity Rating: `2/5`
- Latest Supported RPC Version: `1`
- Added in v5.1.0

**Data Fields:**

| Name | Type  | Description |
| ---- | :---: | ----------- |
| savedScreenshotPath | String | Path of the saved image file |
