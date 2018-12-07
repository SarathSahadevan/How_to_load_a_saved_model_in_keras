# How_to_load_a_saved_model_in_keras

#Step 1

Import all the libraries

Pseudocode

    from keras.models import model_from_json
    import numpy as np

#Step 2

Load the model

Pseudocode

    json_file = open('model.json', 'r')
    loaded_model_json = json_file.read()
    json_file.close()
    loaded_model = model_from_json(loaded_model_json)
    loaded_model.load_weights("model.h5")
    print("Loaded model from disk")

#Step 3

Compile the model with apt optimizer,loss

Pseudocode

    loaded_model.compile(loss='binary_crossentropy', optimizer='adam', metrics=['accuracy'])

#Step 4

Predict

Pseudocode

    def pred ():
        from keras.preprocessing import image
        test_image = image.load_img('image_name.jpg',target_size = (64,64))
 
        test_image = image.img_to_array(test_image)

        test_image = np.expand_dims(test_image,axis = 0)

        result = loaded_model.predict (test_image)

        #training_set.class_indices

        if result[0][0] >= 0.5:
            prediction = 'Its a dog'
        else:
            prediction = 'Its a cat'
    
        print(prediction)
    
    
    
    pred()



ENJOY !!!
