# BindingExtension

[![CircleCI](https://circleci.com/gh/Jintin/BindingExtension.svg?style=shield)](https://circleci.com/gh/Jintin/BindingExtension)
[![jitpack](https://jitpack.io/v/Jintin/BindingExtension.svg)](https://jitpack.io/#Jintin/BindingExtension)

ViewBinding is an amazing tool for Android but it's not so fit in Android development as we still have to do some config. BindingExtension is built to provide a simpler usage.

## Install

Add [Jitpack](https://jitpack.io/) repository to your root `build.grable`:
```groovy
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}
```

Then add dependency in your module `build.gradle`:
```groovy
dependencies {
  implementation 'com.github.jintin:BindingExtension:1.1.0'
}
```

## Usage

### Activity

Extend from `BindingActivity` with your actual `ViewBinding` type then you can use `binding` directly after calling `super.onCreate(savedInstanceState)` and you don't have to call `setContentView` anymore:

```kotlin
class MainActivity : BindingActivity<ActivityMainBinding>() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        binding.label.setText(R.string.activity_label)
    }
}
```

### Fragment

Extend from `BindingFragment` with your actual `ViewBinding` type then you can use `binding` directly after `super.onCreateView(inflater, container, savedInstanceState)` is called:

```kotlin
class MainFragment : BindingFragment<FragmentMainBinding>() {

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)

        binding.button.setOnClickListener {
            binding.button.setText(R.string.fragment_label)
        }
    }
}
```

You can go to ./app module for more information.
## Contributing
Bug reports and pull requests are welcome on GitHub at [https://github.com/Jintin/BindingExtension](https://github.com/Jintin/BindingExtension).

[![Buy Me A Coffee](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/jintin)
