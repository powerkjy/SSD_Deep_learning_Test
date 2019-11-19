>#### What is Virtual Environment??
>##### https://jybaek.tistory.com/791
>##### https://deepmi.me/linux/18791/
>##### https://brunch.co.kr/@hopeless/10
>##### http://pyrasis.com/private/2014/11/30/publish-docker-for-the-really-impatient-book
>##### http://www.kwangsiklee.com/2018/02/%EC%A0%95%EB%A6%AC-ubuntu%EC%84%9C%EB%B2%84%EC%97%90-nvidia-docker-%EC%84%A4%EC%B9%98-%ED%95%98%EA%B8%B0/
>##### http://iamartin-gh.herokuapp.com/ubuntu-16-04-docker-install/

>#### what is SSD
>##### https://jeongchul.tistory.com/529

>#### learning?
>##### http://hrepository.blogspot.com/2018/12/ssd-customizing-with-my-dataset-and.html
>##### https://github.com/balancap/SSD-Tensorflow
>##### https://github.com/weiliu89/caffe/tree/ssd

>#### docker use gui??
>##### https://goodgodgd.github.io/ian-flow/archivers/docker-tutorial
>##### https://www.youtube.com/watch?v=vn5AxBw6bbw
>##### https://www.whatwant.com/entry/tightVNC-Server-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-Ubuntu-1204-1404-1604

>#### frame work
>#### https://m.blog.naver.com/PostView.nhn?blogId=sundooedu&logNo=221195984077&proxyReferer=https%3A%2F%2Fwww.google.com%2F

>#### how to make pbtxt
>##### http://www.birc.co.kr/2018/02/18/object-detection-with-tensorflow-api/

>#### chroling
>##### https://jeongmin-lee.tistory.com/4
>##### https://libsora.so/posts/python-hangul/

>#### make tfrecord
>##### https://github.com/balancap/SSD-Tensorflow/blob/master/datasets/pascalvoc_to_tfrecords.py

>#### use jupyter notebook
>##### http://moducon.kr/2018/wp-content/uploads/sites/2/2018/12/leesangsoo_slide.pdf

>#### tensorflow 1.x -> tensorflow 2.0 code upgrade
>##### https://www.tensorflow.org/guide/upgrade?hl=ko






def main(_):    

    print(os.getcwd())
    writer = tf.python_io.TFRecordWriter('data/train.record')
    # path = os.path.join(FLAGS.image_dir)
    path = 'images/train'
    # examples = pd.read_csv(FLAGS.csv_input)
    examples = pd.read_csv('data/train_labels.csv')
    grouped = split(examples, 'filename')
    for group in grouped:
        tf_example = create_tf_example(group, path)
        writer.write(tf_example.SerializeToString())
    writer.close()
    output_path = os.path.join(os.getcwd(), FLAGS.output_path)
