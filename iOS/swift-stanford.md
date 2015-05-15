# Lecture 8 View Controller Lifecycle, Autolayout

### Common Lifecycle
* viewDidLoad()
    * all of outlets are set   
    * but geometry is not set yet
* viewWillAppear(animated: Bool)
    * geometry is set here, but there are other places to react to gemoetry
* viewDidAppear(animated: Bool)
* viewWillDisappear(animated: Bool)
    * cleanup code
    * not to do time-cunsuming here
* viewDidDisappear()

----

### geometry changed
* viewWillLayoutSubviews() / viewDidLayoutSubviews()
    * autolayout will happen between here

----

### Autorotation
* viewWillTransitionTosize(size: CGSize, withTransitionCoordinator: UIViewControllerTransitionCoordinator)

----

### awakeFromNib
* sent to all object from storyboard 

----


## Size Classes

* Regular
* Compact
* Any

## xcode-autolayout
* update frames
* preview(right-panel)
* always care about magic-number
    * if not necessary : put 0 or Standard