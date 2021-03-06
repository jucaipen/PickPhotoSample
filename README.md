# PickPhotoView

A Library help u to pick photos.

Click to download lastest demo ⬇️ or select [Release Version](https://github.com/Werb/PickPhotoSample/releases)

[![download](/app/src/main/res/mipmap-xhdpi/ic_launcher.png)](https://fir.im/hm38)

## Screenshot

<img src="/screenshots/home.png" alt="screenshot" title="home" width="270" height="480" /> <img src="/screenshots/select.png" alt="screenshot" title="select" width="270" height="480" />
<img src="/screenshots/preview.png" alt="screenshot" title="select" width="270" height="480" />

<img src="/screenshots/list.png" alt="screenshot" title="preview" width="270" height="480" />
<img src="/screenshots/camera.png" alt="screenshot" title="group" width="270" height="480" /> <img src="/screenshots/show.png" alt="screenshot" title="group2" width="270" height="480" />


## Dependency

[![License](https://img.shields.io/badge/license-Apache%202-green.svg)](https://github.com/Werb/PickPhotoSample/blob/master/LICENSE)
[![last-version](https://api.bintray.com/packages/werbhelius/maven/pickphotoview/images/download.svg) ](https://bintray.com/werbhelius/maven/pickphotoview/_latestVersion)

the last-version is this ⬆️

#### Gradle

```
  compile 'com.werb.pickphotoview:pickphotoview:last-version'
```

#### Maven

```
  <dependency>
    <groupId>com.werb.pickphotoview</groupId>
    <artifactId>pickphotoview</artifactId>
    <version>last-version</version>
    <type>pom</type>
  </dependency>
```
#### Eclipse

Sorry ，You are out !

## Usage

Make sure you have permissions about CAMERA and WRITE／READ_EXTERNAL_STORAGE before use

[PermissionsChecker : A Library help u to check permissions on Android M.](https://github.com/Werb/PermissionsCheckerSample)

#### Initialize PickPhotoView

```
  new PickPhotoView.Builder(context)
        .setPickPhotoSize(9)   //select max size
        .setShowCamera(true)   //is show camera
        .setSpanCount(4)       //SpanCount
        .start();
```

#### onActivityResult

```
  @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if(resultCode == 0){
            return;
        }
        if(data == null){
            return;
        }
        if (requestCode == PickConfig.PICK_PHOTO_DATA) {
            List<String> selectPaths = (List<String>) data.getSerializableExtra(PickConfig.INTENT_IMG_LIST_SELECT);
            // do something u want
        }
    }
```

## License

[Apache2.0](https://github.com/Werb/PickPhotoSample/blob/master/LICENSE)

## Last Update (2017.2.5)

#### [v0.0.5-beta5](https://github.com/Werb/PickPhotoSample/releases/tag/v0.0.5-beta5)

1. update image load strategy
2. update image preview strategy
3. optimize memory when load a lot of image
