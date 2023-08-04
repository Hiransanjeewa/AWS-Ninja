
import boto3

def extractVolumeId (volume_arn):
    #Split arn using the colon (':')
    arn_parts = volume_arn.split(':')
    # tghe volume id is the last part of the volue-name after "voulume/"
    volume_id= arn_parts[-1].split('/')[-1];
    return volume_id;


def lambda_handler(event, context):
    
    print(event);

    


    volume_arn = event['resources'][0]
  
    volume_id = extractVolumeId(volume_arn);
    
    ec2_client = boto3.client('ec2')
    
    response = ec2_client.modify_volume(
         
         VolumeId=volume_id,
         VolumeType='gp3',
       
    )
    
    
    
    
#     event = {
#   "version":"0",
#   "id":"0c2a5f83-529c-e4a9-3d06-a748683962be",
#   "detail-type":"EBS Volume Notification",
#   "source":"aws.ec2",
#   "account":"228096628438",
#   "time":"2023-08-04T06:10:58Z",
#   "region":"us-east-1",
#   "resources":[
#       "arn:aws:ec2:us-east-1:228096628438:volume/vol-013e6faad2b03c780"
#   ],
#   "detail":{
#       "result":"available",
#       "cause":"",
#       "event":"createVolume",
#       "request-id":"9c1a7be0-2f73-4523-8e60-4bc3e4c71529"
#   }
# }
    
    
    # print(event)
    # return {
    #     'statusCode': 200,
    #     'body': json.dumps('Hello from Lambda!')
    # }
