---
title: "What's new in Apple Classroom 2.0"
date: "2017-03-28"
---

With iOS 10.3, Apple have released [Apple Classroom 2.0](http://www.apple.com/education/products/#ipad-assistant). Apple Classroom first shipped alongside iOS 9.3 and provided tools to help teachers in an iPad-based classroom.

Apple Classroom provides a range of features including observing student screens, launching apps and URLs and locking student devices.

In the initial release of Apple Classroom, the way that the system worked was that your school Mobile Device Management server had to create and send an "education payload" to teacher and student devices. This payload included information about which users are teachers and students, and which teachers teach which classes and so on. This also prevented students from downloading and using Classroom to control other students' devices.

This made it very easy for teachers in such schools to just pick up and use Classroom. Unfortunately, it made the job rather difficult for school administrators and MDM vendors. So difficult, in fact, that most MDM vendors simply have not shipped support for Apple Classroom. As a result, very few schools are using Apple Classroom to its full extent.

Apple Classroom 2.0 goes a long way to fixing most of these issues.

### Infrastructure Changes

Previously, the infrastructure requirements for Apple Classroom were reasonably high. You needed an MDM server that supported the Apple Education payload and student devices had to be supervised. Essentially, that describes a managed school deployment.

Apple Classroom 2.0 can now work without any of these requirements being met, albeit subject to a range of privacy limitations.

At its most basic, now, anyone can download the Apple Classroom app from the App Store and set up an ad-hoc class. However, the degree of control is limited because of privacy concerns. In Apple's terminology, these ad-hoc classes are called "unmanaged classes" and the MDM-provided classes are called "managed classes".

When a 'teacher' creates an unmanaged class, the class availability is broadcast via bluetooth. A new Classroom section appears in Settings where students can see available classes and join them. There is then a code-based confirmation step, as in many such enrolment systems, and then the 'students' are now in class.

The nice thing about this is that only the teacher device needs to have Apple Classroom installed. The client-side software is built into iOS 10.3 so, as long as all devices are up to date, there is no need to coordinate everyone getting the app installed before you can get to work.

Unmanaged classes, once created, are persistent and by default students will automatically re-join classes when the teacher opens the class in their Classroom app. This can be changed in Settings so that students have to be prompted to join the class before a teacher can control the device. Students can also un-enroll from classes at any time.

As unmanaged classes can be created on any device, the 'student' devices have a lot more control over their visibility and privacy than do students in managed classes provided by a school. In the first place, students can simply not enrol in the class. Secondly, the student has control over two privacy settings: "Lock Apps and Device" and "AirPlay and View Screen". These are two settings, each of which control two features.

Each of these settings has three possible values: Ask, Always and Never. The default for both is Ask. When a teacher tries to lock a device or view a screen, the student sees a permission dialog where they can "Allow" once or "Always Allow".

In a situation where a school has devices supervised in MDM but their MDM does not support creating Managed Classes, there is a restriction that removes students' control over these two settings so that they cannot refuse locking or screen viewing. This is only applicable to supervised devices, so that generally implies institutional control.

It's also worth mentioning that managed classes and unmanaged classes are mutually exclusive. You can't mix and match. If a teacher device has an Apple Education payload installed by MDM, it will not be able to create any unmanaged classes. Similarly, if a student device has an Education payload, it will not be able to join unmanaged classes. Under iOS 10.3, a student in a managed class can look in the Classroom settings, see which classes they are in and see which teachers have access to that class. The privacy controls for locking and screen viewing are hidden in this scenario.

Teachers in BYOD schools where the iOS deployment is not managed in any meaningful way might wonder whether the more general availability of Apple Classroom presents any kind of security or privacy problem for teachers if students were to come into school with Classroom installed on their devices.

Honestly, I don’t think so. In order to exercise control over another iOS device, the ‘teacher’ device has to create a class. The owner of the ‘student’ device then has to:

- Unlock the device
- Go to Settings > Classroom
- Tap on the class name
- Enter a code that’s only displayed on the ‘teacher’ device
- Be accepted into the class by the ‘teacher’ device

That’s a pretty difficult process to go through accidentally.

The other question is about students creating their own unmanaged classes to control other students’ devices. Again, this would require the setup steps mentioned above and students can always delete any unmanaged class that is causing them difficulty. If your school has Apple Classroom support in MDM, turning it on prevents any problems.

### Teacher Features

The major focus of Apple Classroom 2.0 is the loosening of these infrastructure requirements. The update also brings a few new features for teachers.

Firstly, the class list has been redesigned. This now allows you to reorder the classes and is a much more compact representation than the simple screen-wide table view of Classroom that was in Classroom 1.x.

The single new feature in the class view is the addition of a button that will immediately mute all the devices in the class. I'm sure this will be a welcome addition for many teachers! This is simply an action that sets the volume once but doesn't lock it.

The bigger feature in Classroom 2.0 is the enhancement to AirDrop. Classroom 1.x had a Share Sheet extension that allowed you to share URLs from Safari to your class. Classroom 2.0 takes this idea and supercharges it.

Classroom 2.0 has the idea of the "current class". That is, the class that you currently have open in Apple Classroom. This is why the "Close" button in Classroom has changed to "End Class".

While you have a class open, the system-wide Share Sheet gets a new trick. The current class, as well as any sub-groups that you have defined, appear as AirDrop targets at the top of the sheet.

What this means is that teachers can now share a URL, photo, video or any file, to the entire class in one tap. This far exceeds the capabilities of the old Classroom Share Sheet extension that only allowed sending URLs to students. Now, anything that can be AirDropped can be sent to the entire class in one go.

Between Classroom 2.0, recent enhancements to Swift Playgrounds and the new "education edition" 9.7" iPad, someone at Apple is clearly listening to the needs of education.
