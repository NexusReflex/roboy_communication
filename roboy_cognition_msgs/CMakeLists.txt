cmake_minimum_required(VERSION 2.8.3)
project( roboy_cognition_msgs )

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(catkin REQUIRED cmake_modules COMPONENTS
        std_msgs
	geometry_msgs
        message_generation
)

include_directories(
        ${catkin_INCLUDE_DIRS}
)

add_message_files(
    FILES
    AudioData.msg
	AudioInfo.msg
	DirectionVector.msg
	FaceCoordinates.msg
	FacialFeatures.msg
	SpeechSynthesis.msg
	AudioLocation.msg
  RecognizedFaces.msg
  RecognizedSpeech.msg
  IceCream.msg
pose.msg)

add_service_files(
    FILES
    	ApplyFilter.srv
	AssertProperty.srv
	CallQuery.srv
	CheckProperty.srv
	CheckQuery.srv
	CreateInstance.srv
	DataQuery.srv
	DescribeScene.srv
	DetectFace.srv
	DetectIntent.srv
	DriveToLocation.srv
	EvalSeq2Seq.srv
	FindInstances.srv
	FindObject.srv
	GenerateAnswer.srv
	GetObject.srv
	LookAtSpeaker.srv
	OrderIceCream.srv
	PlaySound.srv
	QualityOfTone.srv
	QualityOfTones.srv
    RecognizeFaces.srv
	RecognizeObject.srv
	RecognizeSpeech.srv
	SaveObject.srv
	ShowInstances.srv
	ShowProperty.srv
	ShowPropertyValue.srv
	Talk.srv
	TrainSeq2Seq.srv
	WhichTones.srv
	DetectIceCream.srv
	LocalizeObject.srv

)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

catkin_package( CATKIN_DEPENDS message_runtime std_msgs geometry_msgs
                INCLUDE_DIRS)
